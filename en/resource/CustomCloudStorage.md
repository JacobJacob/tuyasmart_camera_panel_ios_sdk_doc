## Customize cloud storage

User-defined cloud storage,refer to [Tuya Smart Camera SDK - CloudStorage](https://tuyainc.github.io/tuyasmart_camera_ios_sdk_doc/en/resource/CloudStorage.html)

**Declaration**

implement  this TuyaSmartCameraPanelSDKDelegate delegate method:

```objective-c
- (void)cameraPanelSDK:(TuyaSmartCameraPanelSDK *)cameraPanelSDK deviceGotoCameraCloudStoragePanel:(TuyaSmartDeviceModel *)deviceModel;
```

**Parameter**

| Parameter      | Description             |
| ------------- | ---------------------- |
| cameraPanelSDK | TuyaSmartCameraPanelSDK |
| deviceModel    | TuyaSmartDeviceModel    |

**Example**

```objective-c
- (void)cameraPanelSDK:(TuyaSmartCameraPanelSDK *)cameraPanelSDK deviceGotoCameraCloudStoragePanel:(TuyaSmartDeviceModel *)deviceModel {
    NSLog(@"---- deviceGotoCameraCloudStoragePanel");
}
```

