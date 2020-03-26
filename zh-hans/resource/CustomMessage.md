## 自定义消息中心

用户自定义实现消息中心面板，参考 [Tuya Smart Camera SDK - 消息中心](https://tuyainc.github.io/tuyasmart_camera_android_sdk_doc/zh-hans/resource/message_center_list.html)

**接口说明**

遵守  TuyaSmartCameraPanelSDKDelegate 代理中的以下方法:

```objective-c
- (void)cameraPanelSDK:(TuyaSmartCameraPanelSDK *)cameraPanelSDK deviceGotoCameraMessageCenterPanel:(TuyaSmartDeviceModel *)deviceModel;
```

**参数说明**

| 参数           | 说明                         |
| ------------- | --------------------------- |
| cameraPanelSDK | TuyaSmartCameraPanelSDK 单例 |
| deviceModel    | TuyaSmartDeviceModel 数据    |

**示例代码**

```objective-c
- (void)cameraPanelSDK:(TuyaSmartCameraPanelSDK *)cameraPanelSDK deviceGotoCameraMessageCenterPanel:(TuyaSmartDeviceModel *)deviceModel {
    NSLog(@"---- deviceGotoCameraMessageCenterPanel");
}
```

