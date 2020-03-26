## Set Panel

Camera settings panel, which can be configured and displayed through the background dp point [TuyaIPCCameraSDK - Equipment function](https://tuyainc.github.io/tuyasmart_camera_ios_sdk_doc/en/resource/camera_device_points),include：

- device name and icon
- device information(owner,ip,device id, device time zone,wifi signal)
- base setting(Privacy switch, basic function settings, infrared night vision function, picture quality adjustment (brightness, contrast), working mode, etc.)
- Advanced settings (detection alarm setting, PIR switch, power management setting, bell setting, siren adjustment, video layout, pre-point setting, etc.)
- Storage settings (SD card capacity management, formatting, etc.)
- Value-added services (cloud storage purchase, etc.)
- Offline reminder
- Other (Frequently Asked Questions)
- reboot device
- Remove device


**Declaration**

```objective-c
- (UIViewController *)cameraSettingPanelWithDeviceModel:(TuyaSmartDeviceModel *)deviceModel;
```

**Parameter**

| Parameter   | Description               |
| ---------- | ------------------------ |
| deviceModel | TuyaSmartDeviceModel data |

**Example**

```objective-c
UIViewController *vc = [[TuyaSmartCameraPanelSDK sharedInstance] cameraSettingPanelWithDeviceModel:deviceModel]
```

**Panel Display**

![面板示意图](./images/camera_panel_set.PNG)