---
layout: post
title: "Cross Platform code for Mobile - Should I use C++?"
date: 2016-12-30 00:00:00 -0600
comments: true
---

# Summary
When choosing the development approach for mobile development, the idea of cross mobile development always comes up. Write once, deploy everywhere. Do more with a smaller team. There are a number of approaches out there, but which one should you choose and should you?

# Introduction
Will focus on three platforms that are significant in mobile, Android, iOS, and HTML5. Today, these three platforms will reach just about everyone who has a mobile phone.

# Languages
* Android development is done in Java. You can hook in C/C++ with Native Development Kit (NDK).
* iOS development is done in Objective-C, Swift, and you can hook in C/C++.
* HTML5/JavaScript/CSS development is for apps which are embedded into a native app container with native feel using WebKit. Toolkits exist to accomplish this.

# Approaches
The preferential divide occurs because each developer prefers a programming language. You start to think, me and my team can write this in in the language we know best and share my code base. Different approaches have materialized in this pursuit of this perfection.

* Write the code in one language, and cross compile into targeted language.
* Write cross platform code in C/C++, which deploys on every platform known.

In either approach, this doesn't work so well with the UI, because each platform gives you native platform features that you would have to wrap in and would need to be maintained with each native platform release. The web overall recommends we keep UI code in native device language, and backend code in our language of choice. This is logical to me and I tend to agree this is the right approach.

# Options
So what are the some of the options? I won't go into all options, but I want to focus on a few I consider top contenders. With all the options, the backend code will be shared and front end code will be native. This separation of concerns is what enables cross platform development to work well.

## C++ Driven

* C++
* [djinni](https://github.com/dropbox/djinni)
* [FlotBuffers](https://google.github.io/flatbuffers/)

C++ runs on both Android and iOS. As a developer you can create a shared C++ code library to handle all your backend need, then link to this using native coding language. You get optimal running code running, single code base, what's not to love? If you come form a managed language like Java or .NET, you will have to do things like memory management. To make the use of C++ easier, tools exist like Djinni which converts C++ data models into Java code. Developers out there are finding ways to make this easy because there is so much value to be received.

Facebook Memories app took this approach. Read about this at [Post Here](https://code.facebook.com/posts/498597036962415/under-the-hood-building-moments/#).
The company behind PSPDFKit took this approach, and wrote a blog post about it. Read about this at [Post Here](https://pspdfkit.com/blog/2016/a-pragmatic-approach-to-cross-platform/)

### My Perspective
I've never had to write a lot of C++, because everyone is around me is using .NET or Java. So I would have a learning curve. Also, using NDK for Android and JNI for Java to call C++ are both said to be difficult to get working. Even given this, I value learning to use C++ to a great deal for its speed benefits, platform reach, and longevity in the market. Mobile diversity exists today, and C++ is the best answer to having a common codebase across platforms.

## Java Driven
* Java
* [j2Objc](http://j2objc.org/)
* [GWT](http://www.gwtproject.org/)

Developers write backend code in Java which works great for Android. Google loves Java, and they have made all kinds of tools to support that cause. Google developed and has opened sourced the tool called J2ObjC which allows your backend logic is written in Java, and will compile into Objective-C for iOS. You use the Java Classes for Android, and the Objective-C files for iOS. We just achieved common codebase across platforms. The UI in both cases is written in native code and hooks into the Java or Objective-C code. J2ObjC doesn't enable the customization of generated code specifically method names. As a developer who values good method names, you will end up either wrapping them into good method names, or accept them.

Google uses this approach for Google Inbox. Its said that their backend code is identical for their Android, iOS, and Web. To accomplish this for the web, they use GWT which coverts Java to JavaScript. Read about this at [Post Here](https://gmail.googleblog.com/2014/11/going-under-hood-of-inbox.html)

### My Perspective
The biggest advantage is the hope that we can write once and deploy in three areas, Android, iOS, and Web. There are caveats to this. For one, iOS is moving from Objective-C to SWITFT, and getting all the latest performance will require us to move to SWIFT. This is not a problem in the short term, but in the long term will have to reconsider. Another caveat is this isn't a streamlined approach, you will have to figure out how to seamlessly hook everything together and resolve issues as they appear. Which brings me to Google Inbox as showcase to this option. Google engineers have probably spent countless hours to master this approach and resolve countless issues to be successful. How much of the code has if iOS else Android? We won't know because its not open source, but I'm willing to bet there is a plenty of this going on. The one big advantage with Java is using GWT to expose backend data model to the JavaScript Front end and you can also write your JavaScript in Java using GWT. One Java language to rule them all. Sounds good, but should I take the plunge? Google has put there weight behind this approach, but I worry there is to much abstraction, and you end up losing the control you need sometimes to make something great. In the end, its a personal choice.

## C# Driven
* C#
* [Xamarin](www.xamarin.com)

Developers write their mobile applications in C# using Xamarin toolset. Xamarin allows you to write C# code which is converted into native Android code, iOS code and Windows code by default. What makes this approach unique from the others I mention, is they provide Forms that wrap Android UI and iOS UI and wrap all native API access. So even the UI is written C#. There is still separation of concerns where backend code is shared, but UI code are individual projects for each platform. This is because of each platform UI differences. You will still need a MAC to build iOS apps.

### My Perspective
This is the only option I've added which requires a fee to be paid on your build. I love C#, and to be able to program in that language would be great. However, I am not found of the wrapping. The toolset has to be maintained as new versions are released and you may be left behind for a time. Bugs that are appear, are they Xamarin bug or a iOS bug will be hard to track down. Overall, its nice to have a full toolset they offer to build, test, analytics, and etc. This approach is good for enterprises that want the weight of a big player behind them, and also need rapid development across platforms. If I were to go with this approach, I would seriously look at what other paid options I have.

## HTML5 Driven
* [Apache Cordova (Adobe version named PhoneGap)](https://cordova.apache.org/)

Developers write their mobile applications using HTML, JavaScript and CSS. These assets run in a WebView inside a native application container on the target platform. To use native features, plugins are used to expose native features in JavaScript. How does the UI and backend work? The backend is written JavaScript, separate from the frontend JavaScript. This allows separation of concerns.  For UI, mimicking the feel of the platform is exceedingly difficult for a write once approach, and developers generally favor a platform independent UX.

Facebook used this approach for their Mobile App, but the app suffered in performance. There CEO said it was a mistake and moved back to native code. Instagram on the other hand is a Hybrid app that works very well but keep in mind they blend in native code. They are not 100% HTML5, as they want to take advantage of native features like 3D touch.

### My Perspective
The biggest advantage is the ability to build the app using HTML5 which allows developers who already know HTML5 to use their skills to build apps. If you proceed with a platform independent UX, and separate backend logic, you can in theory create 1 UI for iOS, Android, and mobile browsers. Sounds great doesn't it? Practically, you have to adapt to native capabilities on each render to get native features in your app, or lose out in some cases. The native UI will also always outperform a hybrid HTML5 UI. I also feel this approach should allow for a mobile browser HTML render, but developers on the web don't speak of it in this way. Practically again, I don't think it would work because of wanting to integrate native features. Having HTML5, can also allow for hot code downloads, updated HTML5 downloaded into app without having to do a app update through the store. In my opinion, Hybrid HTML5 is good for simple applications that don't need UI performance. HTML5 apps work well for some , for others it doesn't work as well. Decide which is best for you.

# Conclusion
I've shared some approaches to cross platform development. So should I use C++? The choice is up to you. My gut tells me its a good idea, but it also tells me I'll have challenges. I still need to know Objective-C/Swift and Java for the frontend. Native development provides the most flexibility to take advantage of native features. At the end of the day, make the best decision based on you and your teams skillset. The next step for me is to try a approach, and decide to continue based on challenges faced.
