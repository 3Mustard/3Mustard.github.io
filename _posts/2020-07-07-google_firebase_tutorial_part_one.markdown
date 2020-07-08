---
layout: post
title:      "Google Firebase Tutorial Part One"
date:       2020-07-07 17:46:05 -0400
permalink:  google_firebase_tutorial_part_one
---

Welcome to the first part of my Google Firebase and Firestore tutorial.
Google Firebase is a web and mobile app development platform that offers developers many tools to get their apps up and running. 
This first tutorial will focus on what firebase is and how to set it up for a simple application.

Some of the features Google offers are..

1. Cloud Firestore
Store and sync app data at global scale

2. Firebase ML BETA
Machine learning for mobile developers

3. Cloud Functions
Run mobile backend code without managing servers

4. Authentication
Authenticate users simply and securely

5. Hosting
Deliver web app assets with speed and security

6. Cloud Storage
Store and serve files at Google scale

7. Realtime Database
Store and sync app data in milliseconds

8. Google Analytics
Get free and unlimited app analytics

# Lets get started!
First lets setup a cloud firestore which is a no sql database provided by firebase and connect it to a front end application.

1. To get started go to https://firebase.google.com/
Unless you already have a google account you will need to create one. Once logged in return the firebase.google.com and click go to console in the right hand corner. 

2. Here you will see a list of projects if you have any, lets click add new project. Give your project a name and set the location to someplace near you and click create. After a few moments you will be redirected to the projects development screen.

3. To get started with a database look to the options on the left side and click Database. We are going to use the cloud database so click get started with the cloud option. You will be prompted to select production or test mode. Production mode allows you to write a set of rules that decide who can view what. For now lets start in test mode. 

4. Collections in firestore are like tables in SQL. For example if you had a list of users you needed to keep track of, you would have a collection called users that contains data on each user. Each users data would be stored in the users 'Collection' as an individual 'Document'. When you click add collection you will be prompted to add the first document to the collection. Lets create a collection called 'Books' and add the following data for the first book. Firebase will assign a unique id to each document if you desire. 
<img src="https://i.ibb.co/sbdPJTc/step1.png" alt="step1" border="0">

You should now see a collection called books, a document with a unique id and the contents of that document.

<img src="https://i.ibb.co/qYBwxDG/step2.png" alt="step2" border="0">

5. Now that we have a firestore setup with a collection and some data lets connect it to a front end application.
I've created three files for the front end application. 

* app.js
* index.html
* styles.css 

6. let's go back to firebase and click project overview then add project to web app 
<img src="https://i.ibb.co/vqfkXCM/step3.png" alt="step3" border="0">

7. give your project a name and then copy and past the following script tags into index.html 
<img src="https://i.ibb.co/bsNbTT5/step4.png" alt="step4" border="0">

8. Next lets add a line of code in the bottom script under line 42 where firebase.analytics is called. We are going to add a reference to our database by adding `const db = firebase.firestore();`

# Victory!
Our application is now connected and our database is setup. The following github contains the code for a front end that has been setup with firebase [Here](https://github.com/3Mustard/firebase-tutorial/tree/master/setup). If you have been following along all you need to change are the values in the bottom firebase script that contains key value pairs. 

In the next tutorial we will be retrieving data from the firestore.

