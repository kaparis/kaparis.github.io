---
layout: post
title: "Cross Platform Game Development - Introduction"
date: 2017-08-03 00:00:00 -0600
comments: true
---

# Summary
I've been looking into developing a small 2D game as a hobby, but have been undecided on which game engine or framework I should use. This post will cover game engines/frameworks that I narrowed down too. I'll cover my perspective of what drived the short list. 

# List
* love2d
* defold
* corona
* Gidero
* libgdx
* Unity
* Cocos2d-x

# Body
Creating a video game is exciting endeavor. However, where do I start? That was the question I started asking myself. So I search long and hard to build a short list of game engines/frameworks that would give me a startin position.

You're perspective of needs will drive a selection. So let me sum up what I was looking for. I'm a small time developer that wants to work from the source code up, and not rely fully on a GUI editor that does magic behind the scenes. This doens't mean I want to develope from the barebones, so a good toolset was important. I want to use an game engine that is well known and supported. I'm not interested in making a business out of this, so features that game development studios find useful isn't a main criteria for me. My end goal is have the tools to develop a small 2D game as a hobby. 

Age old question of what language is best came to the fore front of my search. I didn't want to learn some special programming language/scripting just for that game engine. GODOT for example using GSCRIPT syntax and even though it supports C++, trying to use that only works against the way it was designed. Unity Script was recently deprecated which is just another reason not to have a game engine specific language. I also wanted a game engine that was cross platform so that I could write once and deploy for Andriod and IOS. When I looked for game engines, what I found was many were using the Lua scripting language. Lua is its own scripting language by it self and isn't tied to a game engine. At first I leaned against game engines using Lua, but I've started to look into them because they offer the advantage of cross platform development with Lua.

# Conclusion
I spent a while searching and I've found a set of game engines that I like to investigate. Its not a complete list, but I feel they have the biggest communities and I won't be a lone ranger. To try them out, I will be developing a small Airplane game in each engine to get a feel of each. In following posts, I will develop the same game for the game engines listed below. I hope to get a feeling of what will work best for me and share what I learn with the community.

I've shared some game engines/framweworks to for Hybrid mobile game development. So what should I use? Remember that Super Mario brothers was built in assembly and the concept of a game engine didn't exist as its known today. We've come a long way there, and we have many tools to support us. At the end of the day, choose the tools based on you and your skillset. I don't think any one way is wrong. The next step for me is to try each approach, and decide an approach that works best for based on challenges faced. Stay tuned.


# Table of Game Engines
| Framework | Open Source | Lang. | Last Release Version | Notes 
| --------- | ----------- | ----- | -------------------- | ------
| love2d    | Yes         | lua   | 0.10.2    2016-10-31 | Active code pushed on Bitbucket|
| defold    | No          | lua   | 1.2.109   2017-07-24 | 
| corona    | No          | lua   | 2016.2830 2016-02-16 | Free version requries a splash screen. No updates for over a year
| Gidero    | Yes         | lua   | 2017.6.3  2017-06-03 | 
| libgdx    | Yes         | Java  | 1.9.6     2017-05-05 | IOS support complicated story
| Unity     | No          | C#    | 2017.1    2017-07-11 | Free version requries a splash screen
| Cocos2d-x | Yes         | C++   | 3.15.1    2017-05-27 | 