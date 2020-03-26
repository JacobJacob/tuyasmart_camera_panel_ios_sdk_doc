## 自定义云存储

用户自定义实现云存储面板，参考 [Tuya Smart Camera SDK - 云存储模块](https://tuyainc.github.io/tuyasmart_camera_ios_sdk_doc/zh-hans/resource/cloud_video.html)

**接口说明**

遵守  TuyaSmartCameraPanelSDKDelegate 代理中的以下方法:

```objective-c
- (void)cameraPanelSDK:(TuyaSmartCameraPanelSDK *)cameraPanelSDK deviceGotoCameraCloudStoragePanel:(TuyaSmartDeviceModel *)deviceModel;
```

**参数说明**

| 参数           | 说明                         |
| ------------- | --------------------------- |
| cameraPanelSDK | TuyaSmartCameraPanelSDK 单例 |
| deviceModel    | TuyaSmartDeviceModel 数据    |

**示例代码**

```objective-c
- (void)cameraPanelSDK:(TuyaSmartCameraPanelSDK *)cameraPanelSDK deviceGotoCameraCloudStoragePanel:(TuyaSmartDeviceModel *)deviceModel {
    NSLog(@"---- deviceGotoCameraCloudStoragePanel");
}
```

