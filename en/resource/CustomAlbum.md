## Customize Album

User-defined local photo album

**Declaration**

implement  this TuyaSmartCameraPanelSDKDelegate delegate method:

```objective-c
- (void)cameraPanelSDK:(TuyaSmartCameraPanelSDK *)cameraPanelSDK deviceGotoPhotoLibrary:(TuyaSmartDeviceModel *)deviceModel;
```

**Parameter**

| Parameter      | Description             |
| ------------- | ---------------------- |
| cameraPanelSDK | TuyaSmartCameraPanelSDK |
| deviceModel    | TuyaSmartDeviceModel    |

**Example**

```objective-c
- (void)cameraPanelSDK:(TuyaSmartCameraPanelSDK *)cameraPanelSDK deviceGotoPhotoLibrary:(TuyaSmartDeviceModel *)deviceModel {
    NSLog(@"---- deviceGotoPhotoLibrary");
}
```

