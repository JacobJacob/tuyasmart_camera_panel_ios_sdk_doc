## Customize feedback under the settings panel

Users can customize feedback in Tuya Smart Camera Settings panel to implement feedback

**Interface**

implement  this TuyaSmartCameraPanelSDKDelegate delegate method:

```objective-c
- (BOOL)cameraPanelSDK:(TuyaSmartCameraPanelSDK *)cameraPanelSDK deviceGotoCustomFeedbackPanel:(TuyaSmartDeviceModel *)deviceModel;
```

**Parameter**

| Parameter      | Description             |
| ------------- | ---------------------- |
| cameraPanelSDK | TuyaSmartCameraPanelSDK |
| deviceModel    | TuyaSmartDeviceModel    |

**Example**

```objective-c
- (void)cameraPanelSDK:(TuyaSmartCameraPanelSDK *)cameraPanelSDK deviceGotoCustomFeedbackPanel:(TuyaSmartDeviceModel *)deviceModel {
    NSLog(@"---- deviceGotoSettingPanel");
  	return YES;
}
```

