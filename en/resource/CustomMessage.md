## Customize Message Center

User-defined implementation of message center panel, refer to  [Tuya Smart Camera SDK - messageCenter](https://tuyainc.github.io/tuyasmart_camera_android_sdk_doc/zh-hans/resource/message_center_list.html).

**Declaration**

implement  this TuyaSmartCameraPanelSDKDelegate delegate method:

```objective-c
- (void)cameraPanelSDK:(TuyaSmartCameraPanelSDK *)cameraPanelSDK deviceGotoCameraMessageCenterPanel:(TuyaSmartDeviceModel *)deviceModel;
```

**Parameter**

| Parameter      | Description             |
| ------------- | ---------------------- |
| cameraPanelSDK | TuyaSmartCameraPanelSDK |
| deviceModel    | TuyaSmartDeviceModel    |

**Example**

```objective-c
- (void)cameraPanelSDK:(TuyaSmartCameraPanelSDK *)cameraPanelSDK deviceGotoCameraMessageCenterPanel:(TuyaSmartDeviceModel *)deviceModel {
    NSLog(@"---- deviceGotoCameraMessageCenterPanel");
}
```

