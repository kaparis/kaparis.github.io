---
layout: post
title: "Cross Platform Game Development - Part 1"
date: 2017-08-14 00:00:00 -0600
comments: true
---

# Summary
Will look into how to build a basic Airplane game using Love2D.

# Info
* Engine/Framework : love
* Open Source : yes
* Language : lua 
* Last Release Version : 0.10.2      
* Last Release Date : 2016-10-31

# Pre-Reqs
* Article considers only a Windows Environment
* Love2D downloaded and files are extracted to a known directory
* You know how to run the CMD Prompt as adminstrator
* You have Andriod IDE installed

# Assests for Game
Download pictures and sound bits here:
https://github.com/kaparis/AirplaneGame/releases/tag/v0.1.0

# Install and Setup
Download Love2D, thats it. :-)

# Development
Create a new folder for game
Create file conf.lua
Create file main.lua

Game Code. Like every game engine, there are three main funtions that need to be implemented. 

  function love.load(arg)
  function love.update(dt)
  function love.draw(dt)

A little know how on game programming, and we have a quick, simple, short game in one file.

In Windows, drag game folder onto the love.exe to run the Game. 

Via the command prompt, enter 
  $ ./love.exe "{your-path}/ScrollingFlying"

Game Screen opens and the game is running.

# Game Distribution

First step is to create a .love file. You need to take the files in your game directory(not the game directory itsel) and bascially zip the files. Then rename the zip extention to .love.

## Windows Deployment (Commnad prompt wiht Adminstrator rights)
  Inside directory where the love.exe is.
  Syntax Example: copy /b love.exe+{name-of-my-game}.love {name-of-my-game}.exe
  $ copy /b love.exe+AirplaneGame.love AirplaneGame.exe

Click on the EXE file and this will run your game. You will still need all the love.exe files always present in the directory with your game.

## Andriod Deployment
Download source from : https://bitbucket.org/MartinFelis/love-android-sdl2/downloads/

Put the game (game.love) in the directory (project)/app/src/main/assets (if this directory don't exist create it). Note the .love must be named "game.love"

mkdir -p assets
cp ~/path/to/your/game/foo.love assets/game.love
ant debug
You should now have a apk that should run on your device located at:
~/bin/love_android_sdl2-debug.apk

Note: I have Andriod Studio, which has the newest version of andriod sdk and ndk which doesn't work with love. So will just directly download those into folders and point to them in the file below.

SDK: Use Version - Latest version is fine.
NDK: Use Version - ndk 14b 

create a file named `local.properties` with contents:
  ndk.dir={add the path to the director here}
  sdk.dir={add the path to the director here}

Run Command
  $ ./gradlew build

## IOS Deployment
NOTE: I don't have a Mac, but below is what you will need to do.

Download source from : (https://bitbucket.org/rude/love/downloads/love-0.10.2-ios-source.zip)

With Xcode, open platform/xcode/love.xcodeproj
Select love-ios target (not love-macosx)
Select Build Phases of the 'love-ios' target and add your 'game.love' file into Copy Bundle Resources.
Build the project.
Your game should appear on your iOS device as an app.

# Opinion
 Creating a game here was super easy. I liked how I had set of tools I could use and I decide how to chain everything. You really feel like you get to the bare bones when creating the game. On the other hand, that means if you are going to make a complicated game, you will need many tools. 

 Game distribution isn't as easy as I hoped. You have to download a prepared project and drop in the game.love file and compile. This has to happen for every platfor you target. 

 Overall, the framework feels in its early days, and isn't trying to be the next commerical game engine. 

# Source Code
https://github.com/kaparis/AirplaneGame

# Credits
Initial guide that I used to create the game on this game engine on on different game engines.
 http://osmstudios.com/tutorials/your-first-love2d-game-in-200-lines-part-1-of-3
