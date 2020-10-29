---
layout: post
title:      "Rails Portfolio Project or Why do we fall"
date:       2020-10-29 04:08:17 +0000
permalink:  rails_portfolio_project_or_why_do_we_fall_sir
---


**The Fall**

For better or worse, I'll always remember this project as the one that put me in my place. Our earlier projects were well within my wheelhouse of experience, and by knocking them out of the park with relative ease, I set myself up for failure through poor time management.

Rails, while not difficult to understand from a "big picture" perspective, is an order of magnitude more complicated and convoluted than Sinatra; there are many more directories and files to mentally keep track of that form several layers. At the bottom of the stack you have raw data in a database, and as you move up through the layers, that data is abstracted into objects, themselves abstracted into complex ideas like end-user authentication or social media posts.

My first attempt at this project, I didn't expect how much time it would take to get all these layers working with each other, and I ended up spending too much of the alotted time on styling. This caused me to rethink how I'd go about it this time, specifically choosing to completely abandon using CSS or Javascript, and instead focusing all of my time and energy on functionality while utilizing a "barebones" aesthetic.


**Like a Newborn Giraffe**

Priorities reconsidered, this time I wanted to build a site that would serve as a Craigslist-type marketplace where people can post their properties for rent. The core functionality would be simple: users register and upon logging in can browse postings, or post their own place. When viewing a specific property, a user can ask questions by messaging the owner of the property, or click the apply button to send a special message allowing the owner to approve the request, removing the property from search results and associating the applicant with the property as a "tenant." 

After establishing how I'd like the site to work, I had to consider the project requirements and whether I'd need to add additional features to meet them. Our cohort lead requested we present our ideas in a one-on-one to get approval and some insight, which I figured would be a great time to ask about how I could meet those requirements; the advice I got was invaluable. Hanaa pointed me in the direction of self-referential associations as a way to use one User model to represent the three types of users on my site: normal users, users who have listed property, and users who are renting property. This single, admittedly complex, association would take care of about half of the project requirements, saving me an immense amount of work. 


**By Your Boot Straps**

While the first half of the project requirements were exclusively association-related, the other half of our requirements involved setting up basic user authentication, third-party authentication (aka: Omniauth), data validation, and the small stuff, like code DRYness, use of helper methods and partials for forms.

During my attempt at the project, I built my authentication system from scratch and it didn't include Omniauth, so I was worried this time around that a new authentication system that met the requirements would be a large chunk of the total project time. However, the new cohort I moved to after failing the project initially included the gem Devise in the lectures. Devise is a rails authentication system that includes data validation, views for authenticated models, Omniauth out of the box, and a straight-forward setup. 

After installing Devise, setting User as the authenticated model, enabling Omniauth and configuring it, I had, again, knocked out nearly the other half of the project requirements. This was astonishing to me, because I had spent so much time building so much of the project from scratch the first time. When we first started learning Ruby, I balked at the idea of utilizing gems as much as possible to eliminate "reinventing the wheel," thinking a scratch-build would always be superior to a one-size-fits-all approach. Only now after failing do I realize that it would be near-impossible to work that way in a professional environment; there just isn't enough time. 


**Learning to Fly**

Ultimately, I feel like this project will end up being my most profound lesson in my entire Flatiron career. Not even just a singular lesson, but an entire box of them applied directly to my face. I came into the project the first time overly-confident in my knowledge and skills, refusing to delegate or supplement with gems, improvising and experimenting with ideas well past when I should have had an entire plan sketched out, and Rails swept my legs out from under me and chuckled. 

Having learned my lesson, dusted my shoulders off, put in my due diligence, I came prepared this time, but I stayed humble and listened to advice. Using what I learned cut my actual work time by 75%, dramatically decreased my stress and resulted in a higher quality end-product that, even without CSS styling, I'm quite happy with. So, remember: We fall so we can learn to pick ourselves up again.
