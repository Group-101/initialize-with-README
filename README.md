

EZTravel App
===



## Table of Contents

[TOC]
## Overview
## Description

This EZ-Travel is basically a smartphone app connect driver-partners and riders. It is designed for travelling from one place to another. The main purpose of this app is to reduce fuel consumption along with providing economical travelling cost hence contributing to green environment and economical for the both end users. As it’s been noticed most of the time people move long distances with having enough space for other individuals in their vehicles. Though there are many other benefits but the most common are these.
•	It will save time, fuel and the travelling cost overall.


## App Evaluation
EZ Travel is a ride-sharing service that provides the EZ-Travel mobile app. Users can use this app to submit trip requests to a destination they want to visit, and this request is then automatically sent to a registered driver near the user. Indicating to the driver the user’s location and whichever driver accepts the requests will drive to the user’s location and the requested location.
This app also calculates the driver’s navigation route automatically. And assists in calculating the distance and fare that will be charged for the trip. The EZ Travel app transfers payment to the driver from the user’s preferred mode of payment.

Product Spec
---
### 1. User Stories (Required and Optional)
There will be two types of persons using this app
1.	Driver
2.	Customer
Both the parties have to register themselves on this platform before using this app.
Features (Required and Optional):

**Required Must-have Stories**
•	Helping a customer to find out a nearby vehicles 
•	Showing Map and  distance from the customer
•	Calculating total distance for customer destination and required time 
•	Sending request to the Vehicle owner
•	Making a deal between customer and Vehicle owner
•	Providing a method for payment 

**Optional Nice-to-have Stories**
•	Displaying a live map of available  vehicles
•	Displaying different packages for different vehicles
•	Offering payment according to selected vehicles
•	Offering a text and voice note facility between customer and  Vehicle owner
### 2. Screens
There are different type of screens which are most commonly going to be used. These are the following,
Login 
•	The user already have an account Register  
•	For the first time user
Vehicle Choice
•	The rider will have this screen
Map Screen
•	The user can share and see the location of their travelling partner
Setting Screen 
•	To modify or change the related settings 

### 3. Navigation
Forced Log-in -> Account creation if no login is available
Vehicle Selection 
Profile -> Text field to be modified.
Settings -> Toggle settings



## Wireframes
---
![](https://i.imgur.com/pCwIzOU.jpg)

### Digital Wireframes & Mockups
![](https://i.imgur.com/uVyo1yk.jpg)
![](https://i.imgur.com/nUKmkjw.jpg)

---
## Schema 
### Models
#### Post

   | Property      | Type     | Description |
   | ------------- | -------- | ------------|
   | RiderId      | String   | unique id for the Riders (default field) |
   | Rider        | Pointer to User| image Rider |
   | image         | File     | image that Rider profile |
   | caption       | String   | image caption by Rider |
   | commentsCount | Number   |Rider Feedback comments |
   Rider Start Point     | Geographical point | Tu find out current loction
   |  Rider drop Point      | Geographical point | Drop point for calculating total distance |
   
   ### Networking
#### List of network requests by screen
   - Home Feed Screen
      - (Read/GET) Query all posts where user is author
         ```swift
         let query = PFQuery(className:"Post")
         query.whereKey("author", equalTo: currentUser)
         query.order(byDescending: "createdAt")
         query.findObjectsInBackground { (posts: [PFObject]?, error: Error?) in
            if let error = error { 
               print(error.localizedDescription)
            } else if let posts = posts {
               print("Successfully retrieved \(posts.count) posts.")
           // TODO: Do something with posts...
            }
         }
         ```
      - (Select pickup point) Enter a pickup location
      - (Select distination) Where to?
      - (Select vehicle ) like Car,Auto,Bike
   - Rider Profile Screen
      - (Read/GET) Query logged in user object
      - (Update/PUT) Update user profile image

##### An API Of Google Maps
- Base URL - [https://developers.google.com/maps/documentation/android-sdk](https://)

   HTTP Verb | Endpoint | Description
   ----------|----------|------------
    `GET`    | /characters | get all characters
    `GET`    | /characters/?name=name | return specific character by name

