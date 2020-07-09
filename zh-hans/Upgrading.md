# 迁移指南

**新版摄像机业务包提供全新的接入方式，通过组件化快速集成多个业务包。接入文档查看 [涂鸦智能摄像机业务包](https://tuyainc.github.io/tuyasmart_bizbundle_ios_doc/zh-hans/pages/ipc_panel/)**

## 集成方式迁移

`Podfile` 引用改为如下形式：

```ruby
source "https://github.com/TuyaInc/TuyaPublicSpecs.git"
source 'https://cdn.cocoapods.org/'

target 'your_target_name' do
  # TuyaSmart SDK
  pod "TuyaSmartHomeKit"
  # 添加设备控制业务包，需要指定固定版本号
  pod 'TuyaSmartPanelBizBundle', 'xxx'
  # 添加摄像机面板业务包
  pod 'TuyaSmartCameraPanelBizBundle', 'xxx'
  # 若需要RN摄像机页面面，请添加摄像机 RN 面板业务包
  pod 'TuyaSmartCameraRNPanelBizBundle', 'xxx'
end
```



## 接口迁移

旧版 SDK 提供 `TuyaSmartCameraPanelSDK` 类来实现摄像机控制面板，新版业务包提供一套组件化方案来调用各个业务包的功能接口。

**注意：** 新版 （TuyaSmartCameraPanelBizBundle） 和旧版 （TuyaSmartCameraPanelSDK）不兼容，不能同时集成。



### 打开面板

**旧版调用方式为：**

```objc
[TuyaSmartPanelSDK sharedInstance].homeId = deviceModel.homeId;
[[TuyaSmartPanelSDK sharedInstance] gotoPanelViewControllerWithDevice:deviceModel completion:^(NSError *error) {
     NSLog(@"load error: %@", error);
}];
```

**切换到新版调用方式：**

> 注意事项查看[涂鸦智能设备控制业务包](https://tuyainc.github.io/tuyasmart_bizbundle_ios_doc/zh-hans/pages/panel/)使用指南

```objc
id<TYPanelProtocol> impl = [[TuyaSmartBizCore sharedInstance] serviceOfProtocol:@protocol(TYPanelProtocol)];
[impl gotoPanelViewControllerWithDevice:deviceModel group:nil initialProps:nil contextProps:nil completion:^(NSError * _Nullable error) {
    if (error) {
        NSLog(@"Load error: %@", error);
    }
}];
```

### 面板事件回调

旧版提供 `TuyaSmartPanelSDKDelegate` 回调面板内事件，新版提供多个 Protocol 回调不同类型的事件。

#### 当找不到设备对应的面板容器时

**旧版调用方式为：**

```objc
#pragma mark - TuyaSmartPanelSDKDelegate

- (nullable UIViewController *)requireSpecialPanelForDevice:(nullable TuyaSmartDeviceModel *)device orGroup:(nullable TuyaSmartGroupModel *)group {

}
```

**切换到新版调用方式：**

针对不同类型的设备，提供不同的 Protocol。例如：

- `TYRNCameraProtocol`：IPC RN 面板。可以选择自行实现，或者直接接入摄像头面板业务包 `TuyaSmartCameraRNPanelBizBundle`
- `TYCameraProtocol`：IPC 原生面板。可以选择自行实现，或者直接接入摄像头面板业务包 `TuyaSmartCameraPanelBizBundle`

自行实现示例：

```objc
[[TuyaSmartBizCore sharedInstance] registerService:@protocol(TYRNCameraProtocol) withInstance:self];

#pragma mark - TYRNCameraProtocol
- (UIViewController *)cameraRNPanelViewControllerWithDeviceId:(NSString *)devId {
    
}
```

```objc
[[TuyaSmartBizCore sharedInstance] registerService:@protocol(TYCameraProtocol) withInstance:self];

#pragma mark - TYCameraProtocol

- (UIViewController *)viewControllerWithDeviceId:(NSString *)devId uiName:(NSString *)uiName {
    
}
```

** 获取预览面板 **

**旧版调用方式为：**

```objc
#pragma mark - TuyaSmartCameraPanelSDK

UIViewController *vc = [[TuyaSmartCameraPanelSDK sharedInstance] cameraViewControllerWithDeviceModel:deviceModel];
[self.nav pushViewControllver:vc animated:YES];
```

**切换到新版调用方式：**

```objc

id<TYCameraProtocol> impl = [[TuyaSmartBizCore sharedInstance] serviceOfProtocol:@protocol(TYCameraProtocol)];
UIViewController *vc = [impl viewControllerWithDeviceId:self.deviceModel.devId uiName:self.device.uiName];
[self.navigationController pushViewController:vc animated:YES];

```

获取或者跳转其它面板，参考新业务包 [涂鸦智能摄像机业务包](https://tuyainc.github.io/tuyasmart_bizbundle_ios_doc/zh-hans/pages/ipc_panel/) 的接口注释说明。

