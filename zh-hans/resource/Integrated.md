## 快速集成

### 使用 CocoaPods 集成

在  ```Podfile``` 文件中加入以下代码：

```ruby
source "https://github.com/TuyaInc/TYPublicSpecs.git"
source 'https://cdn.cocoapods.org/'

platform :ios, '9.0'

target 'TuyaSmartCameraPanelSDK_Example' do
  pod 'TuyaSmartCameraPanelSDK'
  pod 'TuyaSmartHomeKit'
  pod "TuyaSmartPanelSDK"
  
end
```

然后在项目根目录下执行 ```pod update``` 命令，集成第三方库。

CocoaPods 的使用请参考：[CocoaPods Guides](https://guides.cocoapods.org/)

## 项目配置

在对应 Target 中，选择 ```Build Settings```，搜索  ```Enable Bitcode```，设置为 ```NO```。

## 集成 SDK

### 头文件导入

Objective-C 项目在需要使用的地方添加

```objective-c
#import <TuyaSmartCameraPanelSDK/TuyaSmartCameraPanelSDK.h>
```

Swift 请现在  `xxx_Bridging-Header.h`  桥接文件中添加以下内容

```swift
#import <TuyaSmartCameraPanelSDK/TuyaSmartCameraPanelSDK.h>
```

然后在项目在需要使用的地方添加

```swift
import TuyaSmartCameraPanelSDK
```
