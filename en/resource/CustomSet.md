## Customize Set

User-defined implementation setting module, refer to [Tuya Smart Camera SDK - Set](https://tuyainc.github.io/tuyasmart_camera_ios_sdk_doc/en/resource/camera_device_points.html)

**Declaration**

implement  this TuyaSmartCameraPanelSDKDelegate delegate method:

```objective-c
- (void)cameraPanelSDK:(TuyaSmartCameraPanelSDK *)cameraPanelSDK deviceGotoSettingPanel:(TuyaSmartDeviceModel *)deviceModel;
```

**Parameter**

| Parameter      | Description             |
| ------------- | ---------------------- |
| cameraPanelSDK | TuyaSmartCameraPanelSDK |
| deviceModel    | TuyaSmartDeviceModel    |

**Example**

```objective-c
- (void)cameraPanelSDK:(TuyaSmartCameraPanelSDK *)cameraPanelSDK deviceGotoSettingPanel:(TuyaSmartDeviceModel *)deviceModel {
    NSLog(@"---- deviceGotoSettingPanel");
}
```

