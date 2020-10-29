---
layout: post
title:      "Pokedex Go"
date:       2020-03-11 01:08:41 -0400
permalink:  pokedex_go
---

"The World's Greatest Text-Based Pokemon Go Stat Database!"

When I first saw the requirements of our first portfolio project, I knew immediately what I wanted to base it off of. My friends and I have been playing Pokemon Go for a few months now, and if anything was designed to be presented as a list with multiple layers to explore, it's Pokemon.


"Do I Need All Of This?"

For those unfamiliar with the game, it is built around the concept of using your mobile phone's GPS signal to place your avatar on a map that represents the real world. When you move, virtual "you" moves as well. Based on your location, you may run into random creatures called "Pokemon" that you can attempt to capture and use to battle other people's captured Pokemon. There are also special locations called "gyms" that players battle over with the winner earning in-game currency for holding the gym.

Each Pokemon has a plethora of stats that include a range of information, from physical traits like weight and height, through fighting attributes like stamina and attack power, to breeding and evolution data such as what type of egg they hatch from. So, I had decided that I wanted my project to present data from Pokemon... but which data? All the data?


"A User-Base of One"

I realized I had to ask myself, as a player of the game, what data would I find the most useful, and how would I like it to be presented? As I loosely framed how the application's menus would flow I always reminded myself to consider, "Would I enjoy using this?" 

Once I had an idea of what data I'd be presenting, I needed a web-source to scrape it from. Honestly, the choice was easy, because I already used a site on a daily basis to get information about the game. Gamepress.gg ended up being a great source in that not only did it provide all the data I was looking for, but it did so in a scraper-friendly manner.


"A Simple Formula"

During my planning stage, I determined that I would only need three classes: the scraper, the Pokemon and the CLI. It was also easy to visualize how the work would progress: build the scraper and make sure it can collect all the data I need for every entry, then build the Pokemon class to hold all of it, and finally the CLI to present it. 


"Acquisitions Department"

My scraper would consist of four main methods: 

The first would scrape the main list of Pokemon and return an array of the rows the site used to represent each one, in the form of Nokogiri objects. Luckily, the site provided a lot of information about each Pokemon in this main list, most of it invisible when viewing the site. 

The second method would go through each object in the scraped array, and further dismantle it into pieces of data, storing them in a hash, instantiating a new Pokemon object and passing the hash to the Pokemon to populate its attributes. 

The third method would grab the "profile" URL from a specific Pokemon object passed to it, then scrape that page, which contains the rest of the data for that Pokemon, returning the HTML of the page as a Nokogiri object.

Finally, the last method would take the profile HTML and dissect it, collecting it in another hash. Some of the data needs to be stored as hashes within arrays that then go into the main hash. All of this would be passed along through a method within the Pokemon class to the Pokemon object this method is called on.


"What Makes a Pokemon?" 

The Pokemon class is rather simple in its construction: an "@@all" class variable, a list of instance variables representing the attributes of a given Pokemon, the initialize method, a sort method and a method to add additional stats after a Pokemon object was created. I later added a class constant in the form of an array that held the different Pokemon "types," and a method to read it.

The initialize method accepts a hash of attributes, provided by the scraper, and then uses the method "instance_variable_set('@#{key}', value)" within an "each" block to copy each attribute into its proper instance variable. 

The sort method, similarly, is passed a string consisting of the name of the Pokemon attribute you'd like to sort by,  and utilizing a sort block that contains: 

`a.instance_variable_get("@#{method}") <=> b.instance_variable_get("@#{method}")`

which allows the caller to sort the collection of Pokemon by any attribute using only one method.

The "add_stats" method also uses the "instance_variable_set('@#{key}', value)" technique as "initialize" to allow new attributes to be added, or old ones to be changed.


"The Meat and Potatoes"

The CLI class, which represents the entire layout of the application consists of about 2/3rds of the total application code. It contains 18 methods that present menus, create lists, search and sort. Since this is a text-based application, I broke down the repetitive "drawing" of various parts of the interface into smaller methods to keep the code "DRY." I also declared all methods as class methods since I didn't see a need to hold state information.

The flow of the interface begins with a "welcome" method that contains code to resize the terminal window the user is running the application in, a call to the Scraper class to create the initial list of Pokemon, and then a main menu. The main menu presents users with the option to view a list of all Pokemon, view a list of Pokemon of a certain type, search for a Pokemon by name, or exit. When viewing a list of Pokemon, a user is presented with pages containing 15 Pokemon each, with the ability to "turn pages" back and forth, type in the name of a Pokemon to see its profile, or return to the main menu. Once viewing a Pokemon's profile page, you can see basic stats and have the option to view "move sets" which consist of combinations of attack moves that Pokemon can learn, and their effectiveness grade, as determined by the scraped site.


"The Ones We Left Behind"

In the end, I was quite satisfied with how well the application met the requirements of the project. However, during my time developing it, there were a few pieces of "flair" I had planned that never made it in. 

Initially, I wanted an ASCII art representation of each Pokemon to be available on their profile page. There were, of course, normal images of each Pokemon on the scraped site, and I wanted to convert those into ASCII on the fly. I was able to find generic algorithm for doing so, but due to the restricted number of rows and columns of text available to print to in a terminal window, I had to scrap the idea; the images either wouldn't fit or would be so low resolution as to be unrecognizable. 

Toward the end of development, I noticed I really disliked how typing in a number and hitting "enter" to make selections felt; it's clunky and unintuitive. I spent some time devising a solution for capturing keyboard input "unbuffered" so the user would only have to press a key and the application would respond without the necessity of hitting "enter." Once I had that down, I realized I could create a more robust user-interface by creating "buttons" a user could select using the arrow keys, and the buttons could be colored to show which one was "highlighted" for selection. I began writing the code in a separate "Advanced CLI" class, and although I got the mechanics functioning, I didn't have the time to recreate the entire interface in this new style. I do intend to work on implementing it after the project is turned in, however.


"In The End"

What I set out to do was create an application that not only checked the boxes for my cohort's first portfolio project, but also provided a useful experience. To accomplish this, I found ways to present the data that the original website didn't, and delivered the data in a more succinct, easier to digest form. In reality, I suppose it will always be easier to fire up a browser, type in a URL and click a few links than to run a ruby script from an arbitrary device, but while using my application, I feel like I have at least matched the speed and usefulness of the website I scraped. 



