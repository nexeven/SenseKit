# SenseKit

Nexeven Sense™ is an online video analytics platform that provides real-time quality metrics, audience analytics, and marketing analytics..

Much more information can be found at http://www.nexeven.com.

## Install SenseKit using CocoaPods

You can install the CocoaPods tool on OS X by running the following command from
the terminal. Detailed information is available in the [Getting Started
guide](https://guides.cocoapods.org/using/getting-started.html#getting-started).

```
$ sudo gem install cocoapods
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
$ brew update
$ brew install carthage
```

To integrate Sensekit into your Xcode project using Carthage, specify it in your `Cartfile`:

```ogdl
github "Nexeven/Sensekit" ~> 1.0.0
```

Run `carthage update` to build the framework and drag the built `Sensekit.framework` into your Xcode project.

## Install SenseKit manually

1. Download the SenseKit framework for your platform from [URL MISSING]()
2. Drag and drop the framework and make sure it's included in `Embedded Binaries`
3. Import the framework

Objective-C:

```objective-c
@import SenseKit;
```

Swift:

```swift
import SenseKit
```
