---
layout: post
title:      "Sinatra Portfolio Project Naera"
date:       2020-05-25 03:39:27 +0000
permalink:  sinatra_portfolio_project_naera
---


For my second portfolio project, I was tasked with creating a web application that utilized Sinatra and ActiveRecord. The app would allow users to sign up for an account and log in, then create, edit and/or destroy items that would be tracked as a collection associated with the user. 

I came up with the idea for Naera, a calorie and macro nutrient tracker that would allow users to enter nutritional data for the foods they eat. Food data would be associated with dates so the user can see daily totals, and see patterns in their eating habits once they had enough tracked days. 

I determined that my minimum deliverable product would have a landing page with links to pages for registering and logging in. Once logged in, the user would be directed to a summary page for today's date where they can add or delete food items. A navbar would allow the user to navigate to a list of all their tracked days, back to the summary for today, or logout. The list of tracked days would include the ability to add new days or delete existing ones.

To create the filetree setup, I cloned the Fwitter lab I had finished previously and modified or created files as appropriate. It wasn't until later I learned about the gem Corneal and facepalmed. 

My initial design involved associating food items with a single user and multiple days, so you could reuse the foods if they were something you ate often. With this design, the model structure had a user that had many days and many foods, a day model that belonged to user and had many foods through a join-table called days_foods, and a food model that belonged to user and had many days through days_foods.

Once I had built out a good amount of the app, I realized that associating foods with multiple days could become problematic. If, for instance, I wanted to edit a food's values on a specific day, it would affect all other days the food was associated with. Another issue is the weirdness that could occur from trying to add multiples of the same food item to a single day. For these reasons, I decided the best option was for each food entry to be associated with a single day, and if I were to implement reusing foods, simply copy the food entry with a new id and associated day. This design ends up being far less convoluted and easier to work with.

Completing the rest of the project was fairly straight-forward after determining how best to associate the models. I created a users_controller to handle registrations, logins and logouts; a days_controller which handled most of the routing, which included a page for today's summary as well as routes for creating, editing and deleting days; and finally the foods_controller which only handled deleting food items, since their creation was handled in the days_controller while editing a day. 

For my views, I utilized Bootstrap and modified some examples I was able to find offered around the web. While I have some knowledge of HTML and CSS, I wasn't comfortable enough to create from scratch what I wanted the app to look like. I ended up learning quite a bit while modifying the examples to fit my design. One of the neat features of the css and javascript I used was the ability to validate input before sending it through the form. This saved some effort in having to validate and redirect within the route controllers.

In the end, I really enjoyed this project. It felt like building the foundation of a consumer ready product, and I'm looking forward to adding features in the future to push it in that direction.


