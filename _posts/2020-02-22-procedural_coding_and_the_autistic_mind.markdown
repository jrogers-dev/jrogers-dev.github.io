---
layout: post
title:      "Overcoming the Ambiguity of Ruby"
date:       2020-02-22 00:53:19 -0500
permalink:  procedural_coding_and_the_autistic_mind
---

Before my first exposure to Ruby, I had spent a little over a decade working with C style languages; C++ and Java mostly. So, when Flatiron introduced me to Ruby my brain exploded a little when I was shown I can call a method and omit the parantheses. ***"If the parantheses aren't there, how do I know it's a method call and not just a variable?!?!,"*** my instincts screamed. ***"I can return a value just by putting it at the end of a method? I don't need to explicitly state that I'm returning it?"*** I had seen comments about the "magic" of Ruby and how the language is designed around making the code as succinct as possible, but this seemed like madness to me.


However, after a few weeks, I started to ask myself questions like, ***"Does it matter if it's a method or a variable?"***

Dwelling on the subject made me realize, ideally, either should return a value, so it shouldn't matter. 

***"But, what if my method doesn't return a value?"***

With implicit returns, the last line in your method is always the return value; methods will always return values.

**"*Yeah, but what about attributes?! How do you know whether that line of code is accessing an object's attribute or a method?"***

Unlike in Java, where you can give public access directly to an objects internal variables, gaining access to these "attributes" in Ruby requires a getter method for each attribute that returns the value of the attribute. If you're using dot notation on a object in Ruby, from what I've experienced, whatever follows the dot is a method call.


Through this gradual back and forth of reacting to how Ruby is intended to be written, contemplating whether the "C" way is necessary, finding that ultimately the code still makes sense, and sometimes even makes more sense, I'm starting to come to terms with what I originally saw as complete disarray. I'm reminded that just because something has been done a certain way through most of your experience, doesn't mean that is the best or only way. Often, it means there is room for improvement. 
