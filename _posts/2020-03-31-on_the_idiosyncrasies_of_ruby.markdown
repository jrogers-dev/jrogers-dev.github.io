---
layout: post
title:      "On the Idiosyncrasies of Ruby"
date:       2020-03-31 22:05:30 -0400
permalink:  on_the_idiosyncrasies_of_ruby
---


I'm now several weeks into my journey to master Ruby and I've begun to notice odd patterns that seem inherent to the language. For instance, there are often several ways to do any one thing, which initially made me feel uncomfortable with the language. It felt hacked together; a patchwork of ideas from other languages. This feeling of uncertainty led me to look into style guides for a better understanding of the intended syntax, at least according to the community.

After some Googling, I found the initial style guide for Ruby was written by a Bulgarian developer by the name of Bozhidar Batsov. Batsov had recently been hired onto a Ruby development team in which he was the only member with Ruby experience. The other members, while talented, came from different backgrounds such as PHP, Python and Java. Batsov, seeing that a lot of time was being spent on arguing stylistic issues during code reviews, took it upon himself to bring together a set of guidelines from different sources and handed it out as an employee handbook.

Batsov's original handbook would later be published publicly, where it has grown immensely in popularity. Althought well recepted, the community had issues shear magnitude of the document, leading Batsov to create a Gem named "Rubocop" to help developers enforce the guidelines within their own code, without having to memorize all of it.

Through Batsov's guide, I was able to answer the "what" portion of my quandry: I had a massive document that defined which method was deemed the best practice for any given aspect of the language. However, I was still left with the "why." Why was Ruby built this way? Why, at times, can it feel so indecisive about how it wants to be written? Is it a buildup of vestigial code left un-pruned?

My research into Batsov would lead me to the creator of Ruby himself, Yukihiro Matsumoto, and I would find my answer in his zen-like intentions.

Yukihiro started work on Ruby in 1993 as a response to the flaws he saw in the scripting languages of the time, Perl and Python. To him, Perl felt inconsistent and overly-complicated, requiring coders to keep track of data types and context to determine the appropriate functions to use. With Python, the object-orientation felt like a tacked-on afterthought. By focusing on a simple set of design principles, he felt he could create a language with object-orientation at its core that felt light and was easy to write.

The design goal for Ruby started with what Yukihiro felt was the purpose of life: to have joy. For a programmer, joy is most abundant when they are able to concentrate on the creative side of coding instead of being bogged down by syntactical rules. He was able to achieve this goal by utilizing three main principles: conciseness, consistency and flexibility.

Ruby's core was designed with the three principles in mind by treating everything as an object that could be acted on by a universal set of methods. By treating all objects uniformly, the task of tracking what methods work with what data types dissolves and the language feels intuitive with no surprises. This core is also easily extendable through the use of libraries, giving the language great flexibility.

So, in the end, what I initially interpreted as a mashup of techniques that all worked with no logic or reason, was actually the language letting me choose what I was most comfortable with, and having it just work. Ironically, having spent so many years coding in languages with rigid syntax and strict design patterns, I mistook freedom for chaos.
