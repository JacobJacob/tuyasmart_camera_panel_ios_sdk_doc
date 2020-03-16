### Quick integration

Add the following code to the ```podfile``` file:

```ruby
platform :ios, '9.0'

target 'TuyaSmartCameraPanelSDK_Example' do
  pod 'TuyaSmartCameraPanelSDK', :git => 'https://gitlab.com/TuyaSmartCameraPanel/tuyasmart_camera_panel_sdk_ios.git'
  pod 'TuyaSmartHomeKit'
  pod "TuyaSmartPanelSDK", :git => "https://gitlab.com/TuyaSmartPanel/tuyasmart_panel_ios_sdk.git"
end
```

Then execute the `` pod update`` command in the project root directory to integrate third-party libraries.

Please refer to the use of CocoaPods：[CocoaPods Guides](https://guides.cocoapods.org/)

### Project configuration

In the corresponding Target, select `Build Settings`, search for` Enable Bitcode`, and set to `NO`.

### Initialization

TuyaSmartHomeKit version 2.8.0 has been added for security image verification (to continue using the old version can skip steps 1, 2), and enabled the new appkey / secret. Please go to the developer platform to regenerate the required files for SDK initialization and follow the steps below to integrate:

1. Open the project settings, Target => General, and change the Bundle Identifier to the iOS package name corresponding to the Tuya Developer Platform.
2. Import the security image to the project root directory, rename it to t_s.bmp, and add it to "Project Settings => Target => Build Phases => Copy Bundle Resources".
3. Add the following to the project's `` PrefixHeader.pch`` file (Swift projects can be added to the xxx_Bridging-Header.h bridge file):

```objective-c
#import <TuyaSmartHomeKit/TuyaSmartKit.h>
#import "TuyaSmartPanelSDK.h"
#import <TuyaSmartCameraPanelSDK/TuyaSmartCameraPanelSDK.h>
```

Open the ```AppDelegate.m``` file and initialize the SDK in the ```[AppDelegate application: didFinishLaunchingWithOptions:]```  method:

```objective-c
[[TuyaSmartSDK sharedInstance] startWithAppKey:<#your_app_key#> secretKey:<#your_secret_key#>];
```

At this point, the preparations have been completed and the app development can begin. Learn more about TuyaSmartHomeKit access please go to：[TuyaSmartHomeKit Document](https://tuyainc.github.io/tuyasmart_home_ios_sdk_doc/en/)