## 设置面板 - 自定义设备信息

用户在涂鸦智能摄像机设置面板内去自定义实现设备图标，名称的修改

**接口说明**

遵守  TuyaSmartCameraPanelSDKDelegate 代理中的以下方法:

```objective-c
- (BOOL)cameraPanelSDK:(TuyaSmartCameraPanelSDK *)cameraPanelSDK deviceGotoSettingPanel:(TuyaSmartDeviceModel *)deviceModel;
```

**参数说明**

| 参数           | 说明                         |
| ------------- | --------------------------- |
| cameraPanelSDK | TuyaSmartCameraPanelSDK 单例 |
| deviceModel    | TuyaSmartDeviceModel 数据    |

**示例代码**

```objective-c
- (BOOL)cameraPanelSDK:(TuyaSmartCameraPanelSDK *)cameraPanelSDK deviceGotoCustomCameraInfoPanel:(TuyaSmartDeviceModel *)deviceModel {
    NSLog(@"---- deviceGotoSettingPanel");
 		return YES;
}
```

