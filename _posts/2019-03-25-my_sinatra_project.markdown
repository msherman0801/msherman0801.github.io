---
layout: post
title:      "DishBuddy - My Sinatra Project"
date:       2019-03-25 17:50:40 -0400
permalink:  my_sinatra_project
---


For my Sinatra project, I built a website that allows users to search information on restaurants across the United States and Canada. User’s can leave reviews for restaurants, save restaurants to their “DishList”, and follow other user’s restaurant feeds. 

**Why did I choose this project?**

First and foremost, I knew I wanted to use an API (Application Program Interface). I felt as if I understand ruby and everything else we’ve learned so far, including Sinatra, to an extent that would allow me to really tackle this project with an exploratory outlook. So, I based my project around finding an API that interested me and I felt would be usable. I knew, for the sake of the allotted time we had to do this project, I couldn’t use an API that would demand a lot of logic and handle tons of query types. So, I ended up finding an API that really only needed a few different types of queries to make a reasonably complicated application. 

**What API did I use and how did I handle the requests?**

The API I ended up choosing belongs to Zomato.com. It allows keywords for city names, types of restaurant establishments, ratings, and a ton of other cool stuff. The documentation for the API was very understandable and I pretty much knew immediately how I was going to integrate this into my application. I decided that I would simplify the search process for restaurants. User’s can start off just by searching for a city. When they submit the request, the API will return with every similar city name in the US and I displayed those results for the user to choose from. Once they select a city, the API would find what types of eating establishments belong to that city and I would display those results. After they select a type of establishment, the API would return the top rated restaurants that are categorized under that establishment type. The same request and return process would occur for that, and I would display for the user a bunch of information about the restaurant that they chose. 

**When do results from the API get persisted to the database?**

There are multiple requests that are made to the API. There is only one response that could get persisted to the database, and that is the results from the request for the actual restaurant. Information from this request will only get persisted to the database if the user decides to save the restaurant to their “DishList.”

**Where are the relationships and associations between data?**

User data is associated with two other types of data (well sort of). A user can have “friends,” which in this case is synonymous with the user following another user’s “feed.” That being said, there is a join table used to store that relationship between users and their friends. However, a user’s friend is actually just another user. So, the join table is storing a relationship that connects the user table with another entry of the user table.

Additionally, User’s can also have restaurants saved to their DishList, so naturally there is a join table that created the relationships between a User and a Restaurant. Just to break it down a little more: 

1. Users Has many Users Through Friendships
2. Users Has many Restaurants Through UserRestaurants
3. Restaurants Belongs to Users



