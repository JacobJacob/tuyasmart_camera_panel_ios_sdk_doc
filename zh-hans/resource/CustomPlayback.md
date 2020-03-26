## 自定义回放

若提供的回放面板不满足用户需求，用户可自行实现回放面板，参考 [Tuya Smart Camera SDK - 回放](https://tuyainc.github.io/tuyasmart_camera_android_sdk_doc/zh-hans/resource/PlaybackProcess.html)

**接口说明**

遵守  TuyaSmartCameraPanelSDKDelegate 代理中的以下方法:

```objective-c
- (void)cameraPanelSDK:(TuyaSmartCameraPanelSDK *)cameraPanelSDK deviceGotoCameraNewPlayBackPanel:(TuyaSmartDeviceModel *)deviceModel;
```

**参数说明**

| 参数           | 说明                         |
| ------------- | --------------------------- |
| cameraPanelSDK | TuyaSmartCameraPanelSDK 单例 |
| deviceModel    | TuyaSmartDeviceModel 数据    |

**示例代码**

```objective-c
- (void)cameraPanelSDK:(TuyaSmartCameraPanelSDK *)cameraPanelSDK deviceGotoCameraNewPlayBackPanel:(TuyaSmartDeviceModel *)deviceModel {
    NSLog(@"---- deviceGotoCameraNewPlayBackPanel");
}
```

