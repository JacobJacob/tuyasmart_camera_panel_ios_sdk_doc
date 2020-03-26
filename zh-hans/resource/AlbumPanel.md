## 相册面板

摄像机相册面板，展示的是根据设备 id 所保存文件，这些文件是在摄像机预览/回放/云视频播放过程中，本地截图和录制视频。可进行预览，单条删除，全部删除等操作。

**接口说明**

```objective-c
- (UIViewController *)cameraPhotoLibraryPanelWithDeviceModel:(TuyaSmartDeviceModel *)deviceModel;
```

**参数说明**

| 参数        | 说明                      |
| ---------- | ------------------------ |
| deviceModel | TuyaSmartDeviceModel 数据 |

**示例代码**

```objective-c
UIViewController *vc = [[TuyaSmartCameraPanelSDK sharedInstance] cameraPhotoLibraryPanelWithDeviceModel:deviceModel]
```

**面板示意图**

![消息面板](./images/camera_panel_album.PNG)