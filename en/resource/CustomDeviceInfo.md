## Customize device information under the settings panel

The user can customize the device icon and name in the Tuya smart camera settings panel.

**Declaration**

implement  this TuyaSmartCameraPanelSDKDelegate delegate method:

```objective-c
- (BOOL)cameraPanelSDK:(TuyaSmartCameraPanelSDK *)cameraPanelSDK deviceGotoSettingPanel:(TuyaSmartDeviceModel *)deviceModel;
```

**Parameter**

| Parameter      | Description             |
| ------------- | ---------------------- |
| cameraPanelSDK | TuyaSmartCameraPanelSDK |
| deviceModel    | TuyaSmartDeviceModel    |

**Example**

```objective-c
- (BOOL)cameraPanelSDK:(TuyaSmartCameraPanelSDK *)cameraPanelSDK deviceGotoCustomCameraInfoPanel:(TuyaSmartDeviceModel *)deviceModel {
    NSLog(@"---- deviceGotoSettingPanel");
 		return YES;
}
```

