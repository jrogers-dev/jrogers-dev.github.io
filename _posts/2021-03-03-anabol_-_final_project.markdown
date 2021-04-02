---
layout: post
title:      "Anabol - Final Project"
date:       2021-03-03 15:45:47 -0500
permalink:  anabol_-_final_project
---


I decided for my final project to iterate on one of my previous, Naera, because I feel it has the best potential to become a useful, production-level app. Naera was fairly primitive in its functionality in that it simply kept track of nutritional information that you entered manually. Anabol takes this idea several steps farther by interfacing with a nutritional data API, allowing users to look up brand-name foods, associate them with meals on specific days, and save the nutritional information locally.

The technology stack I used to construct Anabol consists of Rails configured as an API using Postgres as its database, React for front end functionality, Redux for state maintenance, TailwindCSS for styling, and the Nutritionix API for accessing nutritional data.

The application’s flow is as follows: at the root url, a user is presented with an informative landing page with options to register an account or log into an existing one. Once registered and logged in, the user is shown a dashboard with navigation links in a sidebar on the left of the screen and a summary of the current day’s meals if any have been entered. From the day summary page, a user can choose to add a food item, which takes the user to a search page where they can search for their desired food and add it to their day as part of their breakfast, lunch, dinner or snacks. Once a food has been added, it will be displayed on the day summary page under a heading for the meal it was added to, and the macronutrient summary will be updated. A user can continue to add or remove foods as they see fit. A calendar page accessible from the left-side navigation links displays all the dates for which there is food data; clicking a date will take you to a summary of that day. 

Future features that will be implemented include the ability to add foods to your pantry as a way of knowing what you have on-hand, but haven’t eaten. The app will then use the foods you have on hand to find recipes that use those foods, with the option to refine the search by diet type, such as ketogenic, vegan, etc.

Ultimately, I think Anabol will be a great SaaS candidate, as it fills a need that many applications have attempted to fill but haven't quite succeeded. While there are innumerable implementations of the calorie/macro tracker, tying in the food you have on-hand, and creating a recipe search function that actually returns recipes, the ingredients for which abide by your chosen restrictions, is really the crux of application that can actually make it worth paying for. 
