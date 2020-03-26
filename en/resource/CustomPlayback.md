## Customize Playback

If the provided playback panel does not meet user needs, users can implement the playback panel by themselves,refer to [Tuya Smart Camera SDK](https://tuyainc.github.io/tuyasmart_camera_ios_sdk_doc/en/resource/camera_function.html)

**Declaration**

implement  this TuyaSmartCameraPanelSDKDelegate delegate method:

```objective-c
- (void)cameraPanelSDK:(TuyaSmartCameraPanelSDK *)cameraPanelSDK deviceGotoCameraNewPlayBackPanel:(TuyaSmartDeviceModel *)deviceModel;
```

**Parameter**

| Parameter      | Description             |
| ------------- | ---------------------- |
| cameraPanelSDK | TuyaSmartCameraPanelSDK |
| deviceModel    | TuyaSmartDeviceModel    |

**Example**

```objective-c
- (void)cameraPanelSDK:(TuyaSmartCameraPanelSDK *)cameraPanelSDK deviceGotoCameraNewPlayBackPanel:(TuyaSmartDeviceModel *)deviceModel {
    NSLog(@"---- deviceGotoCameraNewPlayBackPanel");
}
```

