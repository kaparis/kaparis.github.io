---
layout: post
title: "Cross Platform Game Development - Part 3"
date: 2017-10-26 00:00:00 -0600
comments: true
---

# Summary
Will look into how we will build are basic Airplane game using Corona. When I first looked at this, I saw Corona not updated since 2016. However when I created an account I learned the latest version was March 2017 and daily dev builds are available.

# Info
* Engine/Framework : corona
* Open Source : No
* Language : lua 
* Last Release Version : 2017.3068  
* Last Release Date: 2017.03.31

# Pre-Reqs
* Article considers only a Windows Environment

# Assests for Game
Download pictures and sound bits here:
https://github.com/kaparis/AirplaneGame/releases/tag/v0.1.0

# Install and Setup
Download Corona Suite

You have to enter your email and password to enable the tool. So far this tool feels like it has a commerical level of quality.

Note: There is also Corona Native which provides low-level access to the operating system and native APIs. Allows you to use native languages like Obj-C or Java to pass information between the native code and Lua code. I won't be going into this.

I use Visual Studio Code, and suggest to download Cortona Tools for Visual Studio Code to help in you're development.

# Development
I created a blank project using the Corona Simulator. This creates a folder with a nessary starting files. You start off with a blank main.lua file which is where you program your game.

From here, you open the main.lua file in a editor of your choice and beging writing the code. From here I followed Corona getting started guide which builds astriod game. This gave me a good understanding of how Corona works, and allowed me to develop the airplane game.

Corona is very open to how you build your game. The concepts of a game loop and rendering functions are optional to start. This leads to a very easy start to making a game, and lets you add what you need later on. Overall, I liked Corona direction in the use of Lua to build the game. I appreicated true event handlers unlike defold which does this via messages.

The big advantag Corona had was the Simulator. I would write the code and hit save, the simulator would restart with the latest code in place. This was very natural and streamed line way for me to overcome bugs I had. Corona tools was helping me and wasn't getting in my way.

## Game Distribution
This was really easy. I went to the Corona tool and did File->Build->{Platform}. I filled in some info for my build, and out came a package. Corona can export to Andriod, windows and IOS(needs a Mac). Worked very well. I did notice that in a windows build, my top game guy text was partly covered by the menu bar.

What I was caught off guard by was the need to have a active internet connection during the build. Apparently, Corona phone homes and sends the Lua byte code to select the right build template. So I looked into it and the Corona Enterpise Edition doesn't need to do this. I aslo learned that as of June 2017, Corona Enterpize is now free with the cavet that now a Corona Splash Screen is always shown at the start of the game. That can be disabled if you buy a $99/year Splash Screen plugin. You can find the download of the installer on a post they made on there site about it. However, it doesn't seem like their whole website shows this because when I goto the download section, it says Corona Enterprize can be downloaded for free for 30 days.

# Opinion
I liked Corona a lot. I felt the engine was solid. The simulator was a great tool. I was able to focus code first, without having to learn a game engine gui. This is what I wanted out of my game engine. There is a great online store to buy features instead of building them. So if you a small time game developer, this can be very appealing for low cost and high return. I'm a little reserved that that the build had to contact there server to build a package. I would dependent on Corona being around for a while. This is a freedrom I beleive we have to give up for a good cross platform game engine that has a commerical entity behind it to keep it current.

 # Source Code
 https://github.com/kaparis/AirplaneGame
