# Upgrading

**The new version of the camera device control biz bundle provides a brand-new access method and integrates multiple biz bundle quickly through componentization. [TuyaSmartCameraPanelBizBundle](https://tuyainc.github.io/tuyasmart_bizbundle_ios_doc/en/pages/ipc_panel/)**

## Integrated Migration

The `Podfile` reference is changed to the following form:

```ruby
source "https://github.com/TuyaInc/TuyaPublicSpecs.git"
source 'https://cdn.cocoapods.org/'

target 'your_target_name' do
  # TuyaSmart SDK
  pod "TuyaSmartHomeKit"
  # Add device control biz bundle, need to specify a fixed version number
  pod 'TuyaSmartPanelBizBundle', 'xxx'
  # add cameraBizBundle
  pod 'TuyaSmartCameraPanelBizBundle', 'xxx'
  # add cameraRNPanelBizBundle
  pod 'TuyaSmartCameraRNPanelBizBundle', 'xxx'
end
```



## Interface Migration

The old version of the SDK provides the `TuyaSmartCameraPanelSDK` class to implement the loading camera device control panel, and the new version of the business package provides a set of component solutions to call the functional interface of each business package.

**Note：** The new version (TuyaSmartCameraPanelBizBundle) and the old version (TuyaSmartCameraPanelSDK) are incompatible and cannot be integrated at the same time.



### Open Panel

**The old calling method is:**

```objc
[TuyaSmartPanelSDK sharedInstance].homeId = deviceModel.homeId;
[[TuyaSmartPanelSDK sharedInstance] gotoPanelViewControllerWithDevice:deviceModel completion:^(NSError *error) {
     NSLog(@"load error: %@", error);
}];
```

**Switch to the new calling method：**

> Please check the [TuyaSmartPanelBizBundle] (https://tuyainc.github.io/tuyasmart_bizbundle_ios_doc/zh-hans/pages/panel/) User Guide

```objc
id<TYPanelProtocol> impl = [[TuyaSmartBizCore sharedInstance] serviceOfProtocol:@protocol(TYPanelProtocol)];
[impl gotoPanelViewControllerWithDevice:deviceModel group:nil initialProps:nil contextProps:nil completion:^(NSError * _Nullable error) {
    if (error) {
        NSLog(@"Load error: %@", error);
    }
}];
```

## Panel Delegate

The old version provides `TuyaSmartPanelSDKDelegate` callback events in the panel, and the new version provides multiple Protocol callback events of different types.

### The Callback for Can Not Find Panel Container

**The old calling method is:**

```objc
#pragma mark - TuyaSmartPanelSDKDelegate

- (nullable UIViewController *)requireSpecialPanelForDevice:(nullable TuyaSmartDeviceModel *)device orGroup:(nullable TuyaSmartGroupModel *)group {

}
```

**Switch to the new calling method：**

Different protocols are provided for different types of devices. E.g:

- `TYRNCameraProtocol`：IPC ReactNative Panel. You can choose to implement it yourself, or directly access the IPC ReactNative  Bizbundle `TuyaSmartCameraRNPanelBizBundle`
- `TYCameraProtocol`：IPC Native Panel。You can choose to implement it yourself，or directly access the IPC Native Bizbundle `TuyaSmartCameraPanelBizBundle`

Example：

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

** obtain preview panel **

**The old calling method is:**

```objc
#pragma mark - TuyaSmartCameraPanelSDK

UIViewController *vc = [[TuyaSmartCameraPanelSDK sharedInstance] cameraViewControllerWithDeviceModel:deviceModel];
[self.nav pushViewControllver:vc animated:YES];
```

**Switch to the new calling method：**

```objc
id<TYCameraProtocol> impl = [[TuyaSmartBizCore sharedInstance] serviceOfProtocol:@protocol(TYCameraProtocol)];
UIViewController *vc = [impl viewControllerWithDeviceId:self.deviceModel.devId uiName:self.device.uiName];
[self.navigationController pushViewController:vc animated:YES];

```

Obtain or jump to other panel, Refer to the interface notes of the new business package [TuyaSmartCameraPanelBizBundle](https://tuyainc.github.io/tuyasmart_bizbundle_ios_doc/en/pages/ipc_panel/)

