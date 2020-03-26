## 自定义设置

用户自定义实现设置模块，参考 [Tuya Smart Camera SDK - 设备功能点](https://tuyainc.github.io/tuyasmart_camera_android_sdk_doc/zh-hans/resource/camera_device_points.html)

**接口说明**

遵守  TuyaSmartCameraPanelSDKDelegate 代理中的以下方法:

```objective-c
- (void)cameraPanelSDK:(TuyaSmartCameraPanelSDK *)cameraPanelSDK deviceGotoSettingPanel:(TuyaSmartDeviceModel *)deviceModel;
```

**参数说明**

| 参数           | 说明                         |
| ------------- | :--------------------------- |
| cameraPanelSDK | TuyaSmartCameraPanelSDK 单例 |
| deviceModel    | TuyaSmartDeviceModel 数据    |

**示例代码**

```objective-c
- (void)cameraPanelSDK:(TuyaSmartCameraPanelSDK *)cameraPanelSDK deviceGotoSettingPanel:(TuyaSmartDeviceModel *)deviceModel {
    NSLog(@"---- deviceGotoSettingPanel");
}
```

