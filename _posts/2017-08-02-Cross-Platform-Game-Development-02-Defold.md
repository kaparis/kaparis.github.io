---
layout: post
title: "Cross Platform Game Development - Part 2"
date: 2017-08-28 00:00:00 -0600
comments: true
---

# Summary
Will look into how we will build are basic Aireplane game using defold game engine. This game engine is offered by the King Game studio well knwon for their games like Candy Crush Saga.

# Info
* Engine/Framework : defold
* Open Source : No
* Language. : lua 
* Last Release Version : 1.2.109      
* Last Release Date: 2017-07-24

# Pre-Reqs
* Article considers only a Windows Environment

# Assests for Game
Download pictures and sound bits here:
https://github.com/kaparis/AirplaneGame/releases/tag/v0.1.0

# Install and Setup
As of today, there is Defold Editor 1 that is released and there is Defold Editor 2 in pre-release status. Defold Editor 1 forces you to use Defold servers. Defold Editor 2 allows you to open projects locally. However, the initial project has to be created on there Defold Dashboard Website. An way around this is find a blank project and download that as your starting point. 

You can download the game engine by going to https://www.defold.com/ and logging to access the download section.

# Development
I created a blank project at https://dashboard.defold.com. This lets you download the project offline, and you don't have to visit the website again. When creating the project I selected the box "No, I'll start from a blank slate". From there you open Defold Editor, and open a project From dashboard. This will download the project locally, and we no longer have to work with the Defold Dashboard. Note that the download includes a .git folder since this can be checked into Defold servers. I deleted this as I will host on GitHub.

So I began to create the Airplane game. Basically everything has to be done in the defold editor. There is a game.project file is used to assign game settings like dimenstions. You learn early on that everything lives a GameObject. You have to create gameobjects that can contain sprites, sounds, and scripts. Scripts are written in Lua and every new script comes with 6 default methods which are common in game engines like update().

Working with scripts was a displeasure because of the editor. The editor is far behind tools like VS Code and leaves you wanting a lot. ABout the only things it had was color coding and autocomplete that didn't work so well. Big problem is it didn't have a debugger included. I relied on print statements a lot. To be fair, they do outline how you can use another tool to attach a debugger.

The challenges I faced were learning how to work with the ojbects like factories and GUI. Took a little while, but once you learn its logical. 

Accroding to defold, to keep logic isolated they developed this messageing system. The message is sent by using code like this:

msg.post("default:/enemies/controllerGameObject#enemies", "deleteEnemy", msgdata) 

This specifics a URL of the object that should receive the message. Then the object that receives the message needs to have a if condition to check if that message id (deleteEnemy) was received. It took a while for me to pickup on the correct URL to use. I also am not found of using text that can't catch a error during a build. I ran into a lot of issues during runtime that required a lot of print statements to resolve. In the bigger picture, considering Lua scripting is being used, the choice makes sense.

With some game development know how, I was able to recreate the game in about two weeks of short on and off time. PArt of it was using the GUI to create the world, and the other part was writing Lua script to define actions. I found the balance between the two reasonable.

# Game Distribution
This was really easy. I went to Project->Bundle->my platform and it did all the work to create package. I even got a HTML5 bundle very easily. Just note that the HTML5 bundle won't work by opening the index and needs to be hosted on a web server. You can still run by going to Project-Build HTML5. I did notice that my game menu buttons didn't click though, but I didn't look into why.

# Opinion
I liked Defold but have mixed feelings. Defold editor has all the tools you would need to create a game in one place. I really didn't like the code editor but liked the Defold game design tools. Game distribution was super easy and I love it. 

I went into this wanting to build game from the code up, so having a tool that does so much behind the scenes for you isn't what I wanted. The Defold editor also is literaly one jar file, so working outside the Defold Editor is not the intent of Defold. If for what ever reason Defold doesn't continue to update, you game is trapped. 

# Source Code
https://github.com/kaparis/AirplaneGame
