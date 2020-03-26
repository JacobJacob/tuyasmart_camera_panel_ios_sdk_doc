## Album Panel

The camera album panel shows the files saved according to the device id. These files are local screenshots and recorded videos during the camera preview / playback / cloud video playback process. Can perform preview, single delete, delete all operations.

**Declaration**

```objective-c
- (UIViewController *)cameraPhotoLibraryPanelWithDeviceModel:(TuyaSmartDeviceModel *)deviceModel;
```

**Parameter**

| Parameter   | Description               |
| ---------- | ------------------------ |
| deviceModel | TuyaSmartDeviceModel data |

**Example**

```objective-c
UIViewController *vc = [[TuyaSmartCameraPanelSDK sharedInstance] cameraPhotoLibraryPanelWithDeviceModel:deviceModel]
```

**Panel Display**

![消息面板](./images/camera_panel_album.PNG)