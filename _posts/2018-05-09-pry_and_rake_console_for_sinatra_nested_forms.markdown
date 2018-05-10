---
layout: post
title:      "Pry and Rake Console for Sinatra Nested Forms"
date:       2018-05-10 01:35:20 +0000
permalink:  pry_and_rake_console_for_sinatra_nested_forms
---


A couple of days ago I completed the Sinatra Nested Forms Lab... yes the Pirate! Lab.

I felt pretty good about myself for having accomplished the lab and making all the tests pass successfully.  It wasn't until I watched the video review of the lab that I realized that my pride wasn't all that well deserved.

There's a certain satisfaction with watching the lights turn green on the learn.co page when you pass all the tests.  Unfortunately, a green light, or even the successful completion of a lab, does not always correlate directly to the understanding of the content or objectives of the lab.  I knew how to write the correct code to make the tests pass but not the fundamentals of why THAT code made the tests pass.  I did the readings and code alongs prior to the lab and was able to mimic what I had learned there to make the lab work.  I was a parrot <sigh>.

The video review of the lab was fantastic.  I have to say that whomever the instructor was for that lesson is phenomenal...  not necessarily as a developer (although she definitely was just that), but as an instructor.  She basically broke down every line of code and explained the "Why?" behind it.  The tool that she used to explain was Pry and Rake Console.

I used the crap out of pry when I was building my CLI data app gem project, but honestly, it never really dawned on me to use it when building out these forms in sinatra.  Even during the earliest (and sometimes easiest) portions of the lab, she emphasized the value of dropping into pry to check the work and make sure the code is doing what you expected.  It truly reinforced the ideas of Sinatra Nested Forms.  Instead of simply knowing that to make a nested form I should write something to the effect of: 

name="pirate[ships][][name]"

I now understand what this code is doing and why.  A complex line of code became a simple nested hash.

This is only one snippet of the code...  but the hash will basically come out to something like


params = {"pirate" =>
     {"name" => "a pirate's name",
		 "weight" => "a pirate's weight",
		 "height" => "a pirate's height",
		 "ships" =>
		      [{"name" => "a ship's name",
					"type" => "a ship's type",
					"booty" => "a ship's booty"},
					{"name" => "a ship's name",
					"type" => "a ship's type",
					"booty" => "a ship's booty"}]}}
					
I definitely got a lot out of the video review.  It truly convinced me of the benefit of utilizing pry and rake console in my future endeavors through the course.
					




