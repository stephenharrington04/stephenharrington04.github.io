---
layout: post
title:  "CLI Portfolio Project"
date:   2017-06-14 15:59:20 +0000
---


I've just about finished my CLI Portfolio Project.  All the code is currently working, I think that I've used some pretty good OO Ruby, and not just a bunch of hashes, and I'm feeling pretty good about the product!

Currently, in my personal life, I'm getting ready to move to a new state.  So, my family and I have been doing a lot of house hunting using various websites and mobile apps.  It occurred to me, at the start of this CLI project, that a good app for me to work on would be a real estate search app.

The beginning of the process really centered on whether it would even be possible for me to build an app that could scrape from a public website.  The site that seemed to work the best was Realtor.com.  So, I started out trying to figure out how to get a URL on Realtor.com to come up based on search parameters.  This was a lot of trial and error considering the parameters Realtor.com uses vary and can be blank.  But once I figured out a baseline to go off, it wasn't too bad.

It made the most sense to me to start from the beginning and work to the end from a user's perspective.  That is, get a set of search parameters from a user, parse it into data that is used in specific URLs, create a URL, scrape the data from the URL, and present the data to the user.  Each one of these would be an object.

My first real snag came when creating a scraper.  The Realtor.com sites that I would be scraping from were substantially more complex than the sites we had been using up to this point on Learn.  With the difficulty of scraping these sites has given me a better understanding of the process and shortcuts (not really shortcuts, but a means for finding the data I want more quickly) for the work.  One of the biggest issues I was finding was that based on the given search parameters, usually a list of 15 possible listings was presented on the Realtor.com URL.  One set of code would work for one of the listings, but not on the second, and it be different from the third, and so on.  So, when I was building loops and using pry, the data I wanted would be set to a variable as intended for the first listing, but the loop would break because the data would be in a different place for the second listing.  It was incredibly frustrating.  But again, the process helped me to better understand how to grab data and eventually I came up with code that worked for a single loop.

After getting the scraper set, I started working on the CLI portion of the app.  I thought I was on the home stretch, but man, was I wrong.  It only occurred to me at this point that I wasn't creating objects of listings, I was just taking hashes created by the scraper and displaying that information to the user.  At first it didn't really seem like a big deal, but I realized along the way that I needed a way to save the information that I was scraping somewhere and be able to delve deeper into specific listings.  So, I made a new class:  Listings.  Now the data scraped from the site would be used to created instances of a Listing.  The listings could be created from the hash, and then saved as a class variable, which would then be displayed to the user.  If the user wanted more information about a specific listing, they could select it, the scraper would go to the individual listing, get the information, then add the additional information to that instance of a listing and present it to the user.

The CLI class was also a lot more difficult to create then I anticipated.  I had to create a lot of conditionals to counteract some incorrect actions that a user might input, for example.  But in the end, I feel like the code is pretty clean and it all works.  I've run various tests throughout the process using pry and IRB, and I think I've covered all my basis for different eventualities.

The meat of the app works like this:

-First, the user rubs bundle install.

-Then ruby bin/run.rb

-This starts the CLI class.

-This provides a welcome message and then creates a new instance of an Inputs Class.

-This object is initialized with user inputs that pertain to a zip code, min/max price, number of bedrooms, number of bathrooms, and property type.  Prompts appear to get the inputs, and the only one that needs a specific value is a zip code.

-The CLI class then creates an instance of a parser that has an argument of an instance of a User input.  The parser turns the inputs into strings used by Realtor.com.

-The CLI lass then creates an instance of a URL creator that takes in an argument of an instance of a Parser.  This creates the URL that the information is scraped from.

-The CLI class then calls on the Scraper class with an argument of the URL previously created.

-The CLI class then creates as many instances of listings as needed based on the scraped data.

-The CLI class presents that information to the user at which point the user can start a new search, get more info about a specific listing, or exit.  If the user starts a new search, the process starts over from right after the welcome message.  If they want to exit, a thank you message appears and the app quits.  If they want more info about a specific listing, then the CLI class calls on the Scraper to go to the individual listings URL, scrapes data, adds that additional information to that specific instance of a listing and then presents that information to the user.  At that point, the user is asked if he wants to start a new search, get more info about another previously shown listing, or exit.

