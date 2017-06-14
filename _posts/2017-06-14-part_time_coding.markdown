---
layout: post
title:  "Part Time Coding"
date:   2017-06-14 14:32:06 +0000
---


Learning to code has been a great experience so far.  I've thoroughly enjoyed the challenge and problem solving aspects.  But along with this problem solving comes an inherent requirement for time.  I'm sure coding will come more easily the more experience I gain, but at this point in my coding journey, it still takes me some time to think and problem solve.  To get any solid work done on a lab or project, I feel I need about a good three hour block to work through issues.  One of the issues that I've encountered over the past month is time management.

Life can sometimes get in the way.  Over the past month, my one-year-old son got the chicken pox (that was a fun 2 weeks, let me tell you), I've traveled for work, gone house hunting for an upcoming move, and my eleven-year-old son started his summer break.  Thus, I haven't been able to devote as much time as I had been to this coding class.

The worst part is that all of this started right when I began the first portfolio project.

The one positive that has come out of this time crunch has been a need for me to revisit notes and lessons to reinforce some of the knowledge that I have either forgotten or wasn't as strong at as I remember.  Additionally, I've completed much more personal study.  It's been interesting using rubydocs, rubular, and stack overflow.  I highly recommend using these resources when getting stuck on a particular issue or just to learn new coding techniques.

One in particular that I found was using rescues.  I can't remember if there was a lesson on using rescues or maybe it was in a video lecture, but in any case, I found rescues on stack overflow while working on my CLI portfolio project.

The issue I was having revolved around this:

My app takes in various inputs from a user to create a url.  One of the inputs is a zip code.  It turns out that not every 5-digit combination creates a valid zipcode.  So when the URL is created, no page existed to scrape from, which resulted in my App breaking with a 404 error.  So what I came up with was a method that will check if a 404 error occurs, and if it does, a string will occur telling the user that they entered an invalid zipcode and prompting them to reenter it.  The code looks like this:

```
def self.checker(results_url)
    error_message = ""
    begin
      doc = Nokogiri::HTML(open(results_url))
    rescue OpenURI::HTTPError => e
      if e.message == "404 Not Found"
        puts ""
        puts "!!!! INVALID ZIPCODE ENTERED !!!!".colorize(:red)
        puts "Please enter a valid zipcode".colorize(:red)
        puts ""
        error_message = "404 Error"
      else
        raise e
      end
    end
    error_message
  end
```

That's it for today!
