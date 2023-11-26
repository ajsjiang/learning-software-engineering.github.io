# Building Apple Native Software Using Swift and SwiftUI

## Table of contents
### [Introduction](#introduction-1)
### [Why Use Swift?](#why-use-swift-1)
### [What is SwiftUI?](#what-is-swiftui-1)
### [Starting a Swift Project](#starting-a-swift-project-1)
### [Testing Your App - Unit Tests](#testing-your-app---unit-tests-1)
### [Testing Your App - Simulators](#testing-your-app---simulators-background)
### [Testing Your App - Debugging](#testing-your-app---debugging-1)
### [Other Useful Resources](#other-useful-resources-1)

## Introduction
Swift is a modern, open-source programming language developed by Apple as a replacement for their earlier language, Objective-C.

It can be used on Mac devices to develop software that targets all Apple platforms: iOS, macOS, watchOS, and tvOS, while being deeply
integrated into Apple's IDE: Xcode.

In the following official Apple documentation, there are many other resources, such as videos, interactive demos, and guided
exercises, you can use to better understand and practice these tools.

[Swift Getting Started Documentation](https://www.swift.org/getting-started/)

[SwiftUI Documentation](https://developer.apple.com/documentation/swiftui/)

[Xcode Documentation](https://developer.apple.com/documentation/xcode)

## Why Use Swift?
While languages such as React Native allow you to build multi-platform apps, such as for iOS and Android, using only one source code,
Swift offers many tools that make it easy to quickly build apps that work specifically throughout all of Apple's ecosystem of platforms.

Apps built through Swift can intuitively [support iPhone and iPad screens at the same time](https://developer.apple.com/news/?id=nixcb564),
utilizing design patterns and themes that fit Apple's design policy to match the expected user experience on an iOS device.

You will have access to an [assortment of developer kits](https://developer.apple.com/documentation/technologies?input=kit) that make
it simpler to integrate various, native features into your app. For example, [WidgetKit](https://developer.apple.com/documentation/WidgetKit)
can help set up widgets for iOS Home Screens for your app, or [HealthKit](https://developer.apple.com/documentation/healthkit) can allow you
to communicate to a user's health and fitness data, with their permission.

It comes built-in with over 4000 customizable icons and symbols that are designed to seamlessly match Apple software, which you can view and
modify through [SF Symbols 4](https://developer.apple.com/sf-symbols/).

These are just some of the many advantages available.

## What is SwiftUI?
In 2019, Apple introduced a new framework for building user interfaces called SwiftUI. This is a [declarative UI toolkit](https://www.hackingwithswift.com/quick-start/swiftui/what-is-swiftui), similar to React, where we can tell it what components we want
and the framework will handle performing the steps needed to get that result.

[Hacking with Swift](https://www.hackingwithswift.com) is a great free resource for learning how to do specific things in Swift and SwiftUI
when the issues arise.

## Starting a Swift Project
After launching Xcode, selecting `Create a new Xcode project`, and choosing which platform and type of app you want to make, you will then have
to fill in the following info:

<img width="1512" alt="Screen Shot 2023-03-20 at 4 31 06 PM" src="https://user-images.githubusercontent.com/65694861/226458997-0d9c6227-9ce6-4d34-91b0-58c69b02d016.png">

This information can be changed later, so for starters, you can leave `Team` to be empty, as this is only necessary for deploying the app to the App Store. `Organization identifier` is used to uniquely identify your app once it is up on the App Store, so you can choose whichever name you'd like, such as your name or group's name. Do note `Organization identifier` cannot be changed once the app is uploaded to the App Store but it is purely metadata.

Make sure to use `SwiftUI` and `Swift` as your interface and language respectively, then click `Next` to choose where to store your project, and now you're ready to start.

## Testing Your App - Unit Tests
In Xcode, unit tests are written using the `XCTest` framework. 

You can add a new unit test case by going to `New File` and selecting the `Unit Test Case Class` template:

<img width="726" alt="Unit Test Case" src="https://github.com/NonLan/learning-software-engineering.github.io/assets/95160562/360192fb-40ee-48c0-92d8-9585ad78eb7a">

Xcode will then automatically set up a test case class, and you can write your unit test there.

Unit tests in Xcode work as they do in any other language. One major difference to take note of is that assertions and other functions you may require for unit testing may look a little different since they're a part of the `XCTest` framework. For an outline of this framework and its functions, please refer to Apple's [documentation](https://developer.apple.com/documentation/xctest).

## Testing Your App - Simulators: Background
Xcode has [built-in simulators for many Apple devices](https://developer.apple.com/documentation/xcode/running-your-app-in-simulator-or-on-a-device)
you can use to run your code and see how it performs. 
Simulators in Xcode are a powerful tool for emulating, in real-time, a user’s app experience. You can download new simulators for a specific device and operating system version to test different scenarios, such as an iPhone 11 running iOS 13.

## Testing Your App - Simulators: Setup
To configure a Simulator, go to `Windows` > `Devices and Simulators` and press the plus (`+`) button. You can then specify your configuration. Here, you can pick a simulation device (iPhone 14, iPad Pro, Apple Watch, etc.) in `Simulation`. Depending on the device of your choice, you may need to [download its Simulator runtime](https://developer.apple.com/documentation/xcode/installing-additional-simulator-runtimes).

If you have your own Apple device, you can connect the device to your Mac to use it as your testing environment by connecting it with the appropriate cable and following the on-screen instructions. Note that as of iOS 14, from your device, you will initially have to go to `Settings` > `Privacy & Security` > `Developer Mode` to allow your device to run your app.

## Testing Your App - Simulators: Build and Run
An app can be built and run at any point in time by pressing the play button on the upper-left side of the window. You can do the same, and access additional build options, from `Product`. Note that the simulator will not run if the app cannot be built, and Xcode will highlight the errors that need to be resolved in the leftmost panel. You can also go to `View` > `Navigators` > `Show Issue Navigator` to see these errors.

## Testing Your App - Simulators: Interactions
Once inside the Simulator window, you will notice several new tabs along the top of the Mac to help you in your tests.

The iOS device can generally be interacted with on your Mac as you would on the actual device. For example, swiping and tapping act the same way as they would on a real device. Some other device interactions, like changing the orientation of the device, can be done by going to `Device` and selecting the desired option. Note that some interactions are simulated in a slightly different way than they occur on the real device. They can all be found [here](https://developer.apple.com/documentation/xcode/interacting-with-your-app-in-the-ios-or-ipados-simulator).

The `I/O` tab hosts several options for changing how your Mac handles inputs and outputs, for example, if you'd like to change the output audio device.

The `Features` tab hosts a plethora of features to help test the functionality of your app in a real-time setting. Note that some of these features may not function correctly if your simulated device does not accept the appropriate permissions. For example, to test locational features, you may need to enable these settings in the simulated test environment. Some notable features are as follows, and availability may depend on the simulation device and iOS version:
* FaceID and Authorize Apple Pay can be used to determine how your app handles these cases, if these interactions are ever requested by your app. 
* Toggle Appearance changes the device's view mode setting between light mode and dark mode so that you can see how your app’s UI may change depending on these user settings. 
* Increase/Decrease Preferred Text Size will show you how your app’s UI may change depending on the user’s text size.
* Toggle Increased Contrast will show you how your app’s UI may change depending on whether the user is using their device in increased or regular contrast.
* Location lets you simulate a device location, should your app have any location-dependent services such as CLLocation or MapKit. You can set a current location with latitude and longitude coordinates or simulate device movement with speeds ranging from running on foot to driving on the expressway.

## Testing Your App - Debugging
Xcode hosts its own suite of debugging tools. Breakpoints generally serve as the basis for such debugging. 

You can [set a breakpoint](https://developer.apple.com/documentation/xcode/setting-breakpoints-to-pause-your-running-app) anywhere in your code by clicking the line number at which you want to place the breakpoint. The line number will then be surrounded by the blue breakpoint icon to indicate a breakpoint. You can manage your breakpoints at any time by clicking the `Breakpoint Navigator` in the navigator area.

When you next run your app, the app execution will pause at the site of the breakpoint. You will be able to see your variables in the Variable view in the bottom panel. You can then continue or step through the rest of your code and watch your variables change accordingly by clicking the appropriate buttons in the Debugger console in the bottom panel. For more detailed help with breakpoints and the Debugger console, see [here](https://developer.apple.com/documentation/xcode/stepping-through-code-and-inspecting-variables-to-isolate-bugs).

## Other Useful Resources
[Learn about the different data types in Swift](https://www.hackingwithswift.com/read/0/3/types-of-data). Each language has its own nuances in how
variables are declared and stored, useful to become familiar with it before starting to code.

[SwiftUI has many property wrappers that provide different functionality to the object instances they are attached to](https://www.hackingwithswift.com/quick-start/swiftui/all-swiftui-property-wrappers-explained-and-compared). These are an important tool for making your code efficient and storing your objects properly. In particular, you should be aware of what the `@State` and `@Binding` wrappers do.

[Learn about Protocols for defining properties object models must have](https://www.hackingwithswift.com/read/0/22/protocols). These function similar to what are known as `Interfaces` in other languages. Protocols are important as you will sometimes run into errors that require the object you are using to "conform" to some protocol. For example, if you are trying to loop over a custom object, you must first have that object [conform to Identifiable](https://www.hackingwithswift.com/quick-start/swiftui/how-to-fix-initializer-init-rowcontent-requires-that-sometype-conform-to-identifiable) so that Swift can iterate through a list of that object and recognize which entries are unique.
