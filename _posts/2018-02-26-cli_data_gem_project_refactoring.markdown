---
layout: post
title:      "CLI Data Gem Project Refactoring"
date:       2018-02-27 00:42:49 +0000
permalink:  cli_data_gem_project_refactoring
---


So it's been about 8 months since I last touched coding...  let alone the CLI Data Gem Project.  I had a lot of major life changes occur to include moving, hospitals, and the like.  When I finally came back to the project, I realized (1) I wasn't complete (2) I don't understand what I had already completed and (3), I don't remember anything about programming in Ruby.  These are all slight exaggerations...  but only slight.

The truth was, I felt I needed to start back at the basics.  I reloaded the cirriuculum from the very beginning, pulled out my own notes from the lessons, and started getting to work.

Once I started, a lot of the information that I thought I forgot, started coming back.  In the end, I was able to get through pretty much all the labs and such in a few weeks without too much hair pulling.  It was a great refresher, and helped to solidify some techniques that I felt I was probably shakey on.

When I began working on my CLI project, it wasn't so intimidating as the time before.  I saw where I had one issue remaining before the app would work and completed the process.  However, I also noted a lot of code that seemed out of place, poorly named, and just smelled bad.  SO I started refactoring.

Two of the biggest issues I fixed were classes that stored data that didn't need to be, and objects taking part in CLI rather than letting the CLI take control of it.

I'm happy to say that the app is working even better than before and the code is MUCH cleaner.  The flow seems much more logical, the names of classes now make sense, and the classes take care of their own laundry without interferring with anothers business.  I'm sure there is more refactoring to take place when I actually sit down with an instructor and get someone looking at it with fresh eyes, but I think they will have a lot less work to do in helping me to clean it up.
