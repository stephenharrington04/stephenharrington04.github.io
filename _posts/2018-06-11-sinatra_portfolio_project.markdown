---
layout: post
title:      "Sinatra Portfolio Project"
date:       2018-06-11 16:34:55 +0000
permalink:  sinatra_portfolio_project
---


For my Sinatra Portfolio Project I created a web application called the Pilot Scheduling Web Application.  It allows for two different types of users to sign up, an Instructor Pilot and a Student Pilot, and manage flight information for training.  

For my application, I wanted to provide different levels of access based on the user type, namely if they were an Instructor Vs a Student.  SO I had to devise different validation methods to apply the CRUD principles.

Create:
     - An Instructor Pilot (IP) can create their account
     - An IP can create a Student account
     - An IP can create a Flight
     
     - A Student Pilot (stud) can create their account
     - A stud CANNOT create an IP account OR a Flight

Read:
     - An IP can read any account page or Flight Page
     
     - A stud can read any account page or Flight Page

Update:
     -An IP can edit their own account page
		 -An IP can edit ANY student's account
		 -An IP can edit a Flight for which they are associated
		 -An IP cannot edit another IPs account
		 -An IP cannot edit a Flight for which thet are not associated
		 
		 - A stud can edit their own account page
		 - A stud cannot edit another student's or IP's account page
		 - A stud cannot edit any Flight

Delete:
     -An IP can delete their own account page
		 -An IP can delete ANY student's account
		 -An IP can delete a Flight for which they are associated
		 -An IP cannot delete another IPs account
		 -An IP cannot delete a Flight for which thet are not associated
		 
		 - A stud can delete their own account page
		 - A stud cannot delete another student's or IP's account page
		 - A stud cannot delete any Flight

Having two different types of users with the above CRUD principles seemed relatively easy at first.  I basically had to write a bunch of elsif statements for edit and delete routes.  However, one issue I didn't initially forsee was with the sessions.  If an IP was creating, editing or deleting a student, I had to account for them not being signed in as that student.  Once I realized the issue, it was pretty easy to take care of this through the sessions hash and finding other ways (mainly through email parameters) of storing pertinent information.

I think the most strenuous portion of my app was coming up with all the validations.  It require a lot of thought and a lot of code.  But, like most things, the challenge is what made it both fun and rewarding.  I have a greater appreciation and knowledge of what goes into creating validations as a result of this project.
