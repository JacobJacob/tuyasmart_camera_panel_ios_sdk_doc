## 自定义相册

用户自定义实现本地相册

**接口说明**

遵守  TuyaSmartCameraPanelSDKDelegate 代理中的以下方法:

```objective-c
- (void)cameraPanelSDK:(TuyaSmartCameraPanelSDK *)cameraPanelSDK deviceGotoPhotoLibrary:(TuyaSmartDeviceModel *)deviceModel;
```

**参数说明**

| 参数           | 说明                         |
| ------------- | --------------------------- |
| cameraPanelSDK | TuyaSmartCameraPanelSDK 单例 |
| deviceModel    | TuyaSmartDeviceModel 数据    |

**示例代码**

```objective-c
- (void)cameraPanelSDK:(TuyaSmartCameraPanelSDK *)cameraPanelSDK deviceGotoPhotoLibrary:(TuyaSmartDeviceModel *)deviceModel {
    NSLog(@"---- deviceGotoPhotoLibrary");
}
```

