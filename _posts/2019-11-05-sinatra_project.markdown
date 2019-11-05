---
layout: post
title:      "Sinatra project"
date:       2019-11-05 18:24:09 +0000
permalink:  sinatra_project
---


If you read the blog about my first project you know that enviroment/gem issues have given me more trouble then the actual coding assignments have. This project was no exception. My gem version of sqlite3 was locked at a version that wouldn't allow me to run rake migrations successfully. I tried specifying a different version of sqlite3 but this made all rake commands throw an error that despite my new gemlock file being version 1.3.13 that my program was trying to use 1.4. I tried deleteing all versions of sqlite3 and the gemlock before bundling with the desired version but I was still given the same error. To fix this I had to specify a stable version of sqlite3 that went along with a stable version of active record. 

original error:
rake aborted!
LoadError: Error loading the 'sqlite3' Active Record adapter. Missing a gem it depends on? can't activate sqlite3 (~> 1.4), already activated sqlite3-1.3.13. Make sure all dependencies are added to Gemfile.
Gem::LoadError: can't activate sqlite3 (~> 1.4), already activated sqlite3-1.3.13. Make sure all dependencies are added to 
Gemfile.

the fix:
gem 'sqlite3', '1.3.13'
gem "activerecord", github: "rails/rails", branch: "5-2-stable", :require => "active_record"

After clearing up this issue I had little trouble completeing the assignment.
I purposly left out some features and css that I want to incorporate into this web app so that I have something to work on in my free time that will keep my coding skills from getting rusty and challenge my abilities. 

I really enjoyed this project because it finally feels like I can create something useful.
