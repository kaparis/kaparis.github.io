---
layout: post
title: "Hybrid Mobile Development - What should I use?"
date: 2017-05-01 00:00:00 -0600
comments: true
---

# Summary
Mobile development teams today most commonly use a silo approach to building mobile applications. Each mobile platform application is written in a separate programming language, using the platforms  native tools. The three major platforms are iOS/Objective-C/XCODE, Android/Java/Android Studio, and Windows/C#/Visual Studio.

This has meant maintaining three code bases for the same platform, which is time intensive and costly. So the industry has looked into ways to solve this. In a previous post, I looked at how code reuse could be done at a programming language level. In this post I will discuss probably the four most talked about or researched approaches to achieve Hybrid Mobile Development. This doesn't cover every approach available; We have a very talented industry which has found endless ways to solve the same problem.

# Introduction
Below is a list of the frameworks that we will cover and the different philosophy's that drive how to produce Hybrid Applications.

Will look at these four hybrid frameworks
* [Ionic 2](http://ionicframework.com/) (Developed by Drifty Co.)
  * Write once, deploy everywhere.
* [React Native](https://facebook.github.io/react-native/) (Developed by Facebook Team)
  * Learn once, write anywhere.
* [NativeScript](https://www.nativescript.org/) (Developed by Telerik Team)
  * One Code base, native deploy everywhere.
* [Xamarin](https://www.xamarin.com/) (~~Developed~~ Owned by Microsoft)
  * Cross platform mobile apps using C#

## What the web says
A indicator of a technology relevance is the people who search for it. So I looked at Google trends and Github Pulse.

[Google Trends](https://trends.google.com/trends/explore?date=today%2012-m&q=Ionic,React%20Native,NativeScript,Xamarin) - Last 12 Months - World Wide Interest In Order of Rank
1. Ionic (More Interest in USA)
2. Xarmin (World Wide Interest)
3. React Native (More interest in China)
4. NativeScript (More interest in the USA)

Github - April 2017 Pulse - In order of rank of # of Authors
1. React Native
  * 418 commits | 119 authors | 2982 watch | 47,839 stars
2. Xarmin
    * Andriod : 60 commits | 9 authors
    * iOS : 169 commits | 26 authors
3. Ionic
  * 169 commits | 26 authors | 1733 watch | 29,330 stars
4. NativeScript
  * 75 commits | 15 authors | 602 watch | 10,088 stars

# Ionic 2
Ionic is a combination of two technologies, Apache Cordova(AKA PhoneGap) and AngularJS. Apache Cordova provides the native app container with a Webview to run HTML/CSS/JS and expose native features via JavaScript. With just Cordova, you start with a blank canvas and can use any web frameworks out there. AngularJS is a JavaScript framework which solves the many challenges in developing single-page applications. Ionic married Cordova to AngularJS and provides foundation which you can use to paint your canvas.

## My Opinion
For someone coming from the web, you can in theory write most of your mobile application using HTML5/CSS/JS. Some drawbacks is the interface isn't native looking unless you mimic it with HTML. Another drawback is this probably isn't the right choice for optimal performance. Don't choose this if you know your going to build graphically intense apps.

# React Native
React Native is a extension of React.js. React Native allows you to build your app using JavaScript and the GUI in JSX, which then actually uses the native components behind the scene. So you get all the speed benefits of native, but get to write it in JavaScript and JSX.

## My Opinion
For someone coming from React.js, you can easily ease into the framework and get all the benefits of native speed. However, it means learning React Native syntax and way of developing. Its an investment that assumes React Native can be relied on to do the rest with minimal effort from you. Facebook actively uses this, so its a testament that it works. Recall that Facebook tried to build a mobile application with HTML years back, but decided to go back to native because of performance. They have found a new way to accomplish cross platform and it seems to be working well for them.

# NativeScript
NativeScript is similar to React Native. You use JavaScript or TypeScript along with AngularJS to build the app. NativeScript uses native UI code, even though you are writing the code in TypeScript/JavaScript. So you get all the speed benefits of native, but get to write it in TypeScript/JavaScript and AngularJS.

## My Opinion
The key advantage NativeScript has is that you can use TypeScript. Once you use TypeScript, you'll never want to go back to JavaScript.

# Xamarin
Developers write their mobile applications in C# using Xamarin toolset. Xamarin allows you to write C# code which is converted into native Android code, iOS code and Windows code by default. What makes this approach unique, is they provide Forms that wrap Android UI and iOS UI and wrap all native API access. So even the UI is written C#. There is still separation of concerns where backend code is shared, but UI code are individual projects for each platform. This is because of each platform UI differences. You will still need a MAC to build iOS apps.

### My Perspective
This is the only option I've added which requires a fee to be paid on your build. I love C#, and to be able to program in that language would be great. This approach is good for enterprises that want the weight of a big player behind them, and also need rapid development across platforms. If I were to go with this approach, I would seriously look at what other paid options I have.

# Conclusion
I've shared some approaches to Hybrid Mobile development. So what should I use? React Native is very active on Github, and Facebook has invested greatly in it. The investment to learn there way may be a good choice. A simple fact is that native development provides the most flexibility to take advantage of native features. At the end of the day, make the best decision based on you and your teams skillset. I don't think any one way is wrong. The next step for me is to try a approach, and decide to continue based on challenges faced.
