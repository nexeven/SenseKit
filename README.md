# SenseKit

Nexeven Sense™ is an online video analytics platform that provides real-time quality metrics, audience analytics, and marketing analytics.

Much more information can be found at http://www.nexeven.com.

## Install SenseKit using CocoaPods

You can install the CocoaPods tool on macOS by running the following command from
the terminal. Detailed information is available in the [Getting Started
guide](https://guides.cocoapods.org/using/getting-started.html#getting-started).

```
sudo gem install cocoapods
```

### Add SenseKit to your iOS app

CocoaPods is used to install and manage dependencies in existing Xcode projects.

1. Create an Xcode project, and save it to your local machine.
2. Create a file named `Podfile` in your project directory. This file defines
   your project's dependencies, and is commonly referred to as a Podspec.
3. Open `Podfile`, and add your dependencies. A simple Podspec is shown here:

```ruby
platform :ios, '8.1'
pod 'SenseKit'
```

4. Save the file.
5. Open a terminal and `cd` to the directory containing the Podfile.

```bash
cd <path-to-project>/project/
```

6. Run the `pod install` command. This will install SenseKit.

```bash
pod install
```

7. Open your app's `.xcworkspace` file to launch Xcode.
   Use this file for all development on your app.

## Install SenseKit using Carthage

[Carthage](https://github.com/Carthage/Carthage) is a decentralized dependency manager that builds your dependencies and provides you with binary frameworks.

You can install Carthage with [Homebrew](http://brew.sh/) using the following command:

```bash
brew update
brew install carthage
```

To integrate Sensekit into your Xcode project using Carthage, specify it in your `Cartfile`:

```ogdl
github "Nexeven/Sensekit" ~> 1.0.0
```

Run `carthage update` to build the framework and drag the built `Sensekit.framework` into your Xcode project.

## Install SenseKit manually

### Download SenseKit

First we need to download SenseKit. Download the latest version from the link below.

[https://github.com/nexeven/SenseKit/releases](https://github.com/nexeven/SenseKit/releases)

### Unzip SenseKit

After you download SenseKit extract it somewhere. It will look like something this:

![SenseKit](https://s17.postimg.org/djhr9gzfj/Sense_Kit1png.png)

### Move `SenseKit.framework` to your project's directory

Move the `SenseKit.framework` file equivalent to your platform (iOS, Mac, tvOS) to your application's directory. In our example we moved it to the `Frameworks` directory next to our Xcode project, but you can move it anywhere you want.

![SenseKit](https://s11.postimg.org/q6hw4l4pf/Sense_Kit2.png)

### Drag and Drop `SenseKit.framework` into your Xcode project

Now you just need to drag and drop `SenseKit.framework` into the **Embedded Binaries** section in your target configuration.

![SenseKit](https://s11.postimg.org/bawbap1gj/Sense_Kit3.gif)

## Configuring the plugin

Now just import the framework and configure the plugin using your instance of `AVPlayer` and your customer info.

#### Objective-C

```objective-c
@import SenseKit;

...

NECustomMetadata *assetMetadata = [NECustomMetadata alloc];
assetMetadata.key = @"AMK1";
assetMetadata.values = @[@"AMV1", @"AMV11"];

NECustomMetadata *viewerMetadata = [NECustomMetadata alloc];
viewerMetadata.key = @"CMK1";
viewerMetadata.values = @[@"CMV1", @"CMV11"];

NESenseAgent *agent = [[NESenseAgent alloc] initWithAVPlayer:player // your AVPlayer instance
                                                     assetId:assetId
                                                  serverHost:@"https://sense.nexeven.io"
                                                      nxeCID:@"BBQCID"
                                                   assetType:assetType
                                                   assetName:assetName
                                                    viewerId:@"jorgenS"
                                               assetMetadata:@[assetMetadata]
                                              viewerMetadata:@[viewerMetadata]];
```

#### Swift

```swift
import SenseKit

...

let assetMetadata = CustomMetadata()
assetMetadata.key = "AMK1"
assetMetadata.values = ["AMV1", "AMV11"]

let viewerMetadata = CustomMetadata()
viewerMetadata.key = "CMK1"
viewerMetadata.values = ["CMV1", "CMV11"]

let agent = SenseAgent(
    player: player, // your AVPlayer instance
    assetId: assetId,
    nxeCID: "BBQCID",
    assetType: assetType,
    assetName: assetName,
    viewerId: "jorgenS",
    assetMetadata: [assetMetadata],
    viewerMetadata: [viewerMetadata]
)
```

