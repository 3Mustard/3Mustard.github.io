---
layout: post
title:      "Rails api with Javascript frontend"
date:       2020-01-22 18:03:23 +0000
permalink:  rails_api_with_javascript_frontend
---


For my Javascript/rails project I took an idea I had used for the cli project and created an app that uses a deck of tarot cards to give the user a three card draw to give them insight into a question. 
This is the first project where I decided to use a different database. The Json file I wanted to seed my database with contained arrays and sqlite3 did not support this type of column so I went with Postgre. 

With the database setup and seeded I proceeded to set up my controllers with the CRUD methods I intended to use and some rough idea of what I would be passing to these methods.

Next I wrote down how I wanted the site to look and how the features would work. From there I built out my js classes for a fortune,  a card and a menu. 

I tried to build functions that handled one specific task so they could be reused in another context or be changed around to adapt to new features and ideas. For every function I wrote I carefully console.logged my variables to be sure I was giving and getting the desired inputs and outputs.

My biggest struggle came down to styling everything once I was happy with the functionality.
I played around with css for a long time with no real success. Eventually I decided on using bootstrap styles which simplified things a lot and left my app with a clean scalable look.

Moving foreward I'd like to improve my css skills and learn more about bootstrap.

I really enjoyd working on this project as I got to create an app that I had wanted to make since I first started coding.
I tried to make it in python almost a year ago before learning I'd need to use a webframework, html,css, and javascript. All of which I had no experience using. 
