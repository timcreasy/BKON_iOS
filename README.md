# Integrate the phySDK to a new or existing Swift project

### Introduction
The [phySDK](https://www.phy.net/sdk/physical-web-sdk-ios/) is a powerful tool for detecting, and interacting with both iBeacon and Physical Web beacons in a single application.

[BKON Connect](https://bkon.com/) is the leading inbound proximity marketing platform. Based in Nashville, TN, BKON Connect makes hardware and software for the Physical Web.

### Requirements

iBeacon technology depends on Core Location, support for which was added in iOS 7.  Although Physical Web beacons do not depend on this, if you would like to support both, please target iOS 7 or later with your application.

You will need the latest version of [Xcode](https://developer.apple.com/xcode/downloads/).

This guide will not go through the process of setting up an iOS application project using Swift. However, this guide can be used on any new or existing Swift project.

### Guide

Adding the phySDK to an existing Swift project requires a few simple steps.  Because the phySDK is written in Objective-C, it will require adding a bridging header to your project.

First, let's add the phySDK to our project.  Navigate to File -> Add Files to "PROJ_NAME"... and select the PhySdk.framework file which can be found in your downloaded copy of the phySDK:

![](http://i.imgur.com/uP6MmbV.png)
![](http://i.imgur.com/8exSQxO.png)

Next, we will need to add a bridging header file to our project, to allow us to use the BKON Mobile Objective-C methods in our Swift project.

To begin, we need to create a new Objective-C file to act as the bridging header.  Navigate to File -> New File

![](http://i.imgur.com/h1vkL8n.png)

Select Objective-C file, and follow the naming convention: PROJ_NAME-Bridging-Header, as is depicted in the following:

![](http://i.imgur.com/sXXDavB.png)
![](http://i.imgur.com/8PugTrz.png)

A prompt will appear, asking if you would like to configure an Objective-C bridging header.  Select "Create Bridging Header":

![](http://i.imgur.com/8rpY2cY.png)

You can ensure that this Objective-C bridging header has been configured in your project by selecting your project in the sidebar -> Build Settings -> Search "Objective-C Bridging Header".  Ensure that your newly created file is listed:

![](http://i.imgur.com/YwZgvC3.png)

With our newly created bridging header, we can import the necessary headers which we would like to expose to our Swift project. In this case, we will be importing PhySdk.h. Open your newly created PROJ_NAME-Bridging-Header.h and add the following:

![](http://i.imgur.com/fMpWnHV.png)

That's it! Depending on what headers you exposed to Swift, they will now be available to use in your Swift Project!

![](http://i.imgur.com/EJvmWd0.png)