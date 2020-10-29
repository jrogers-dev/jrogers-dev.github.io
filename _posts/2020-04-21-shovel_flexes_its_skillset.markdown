---
layout: post
title:      "Shovel Flexes Its Skillset"
date:       2020-04-21 00:50:48 -0400
permalink:  shovel_flexes_its_skillset
---

First, a haiku. 

 

*His great strength pushes*

*Forcing them into one space*

*He sighs longingly*

 

For quite some time, as I imagine is the case with many beginning Rubyists, I looked at shovel as my trusty tool for concatenating strings and pushing values onto arrays with the assumption that this was its sole purpose. It makes sense: it shovels whatever is on the right of it onto whatever is to the left. However, shovel's simple appearance actually hides a rather varied set of uses and some interesting idiosyncrasies. 

**Objection Sustained**

When we concatenate strings with shovel, it's easy to look at it as an exact replacement for the "+=" operator. But, if we... dig... a little deeper, there's a major difference between the two. 

```
varA = "A" 
=> "A"

varB = varA 
=> "A"

varA += "BCD" 
=> "ABCD"

varB 
=> "A" 
```

Using "+=" we see that even though we changed varA to "ABCD" varB is left unchanged, still showing varA's previous value of "A" 

```
varA = "A" 
=> "A"

varB = varA 
=> "A"

varA << "BCD" 
=> "ABCD"

varB 
=> "ABCD" 
```

But, if we use "<<", suddenly both varA and varB have changed. This is because variables don't actually hold values, they point to objects in memory that hold values. The object, "A", is created in memory and our variable, varA is kind of like a sticky note that has the memory address of object "A" written on it. Whenever we use varA, Ruby looks at, reads the address and then grabs the object from that address. 

In our first example, varA is pointing to a String object with the value of "A" and varB is told to also point to that same object. When we use "+=" a new String object is created in memory with a value of "ABCD" and varA is told to point at it, while varB continues to point at the original String object containing just "A".  

In our second example, the setup is the same, with varA pointing to a String object with a value of "A" and varB pointing to that same object. However, when we use "<<" we modify the String object holding "A" so that it now holds "ABCD" but remains at the same address. In this case, neither varA nor varB changed what they were pointing to, so when we edited the object they both return the new value. 

 

**The New Meta**

```
class << MyClass 

    def aClassMethod 

        p "This is a class method" 

    end 

end 
```

Honestly, the metaclass concept deserves an entire dedicated post to thoroughly explain, but for now think of the metaclass as a hidden class that exists as a direct ancestor to any object, but only that object; every instance of every class has its own unique metaclass that inherits from its ancestor's superclass.  

Using the shovel operator between the keyword "class" and a class name causes any method defined within the following block to be a class method without the need to prefix each one with "self" because we are defining it within the metaclass of "MyClass." 

However, while the details of how this works is intriguing, I haven't thought of a good reason to use it. Using the "self" prefix or using dot notation to define methods on an existing object seem more readable.

**Bit Shifting**

```
2 << 2 

=> 8 
```

Operators that manipulate their operands at the bit level are known as "Bitwise Operators." Again, bitwise manipulation deserves at least an entire post if not an entire book to comprehend completely, but if you understand how an integer is represented in bit form, shifting is a simple idea to grasp. 

The left shift functionality of shovel works by taking the left integer's bit form and shifting each bit to the left by the value on the right of the shovel. In our above example, the left integer, two, is represented in bit form as: 

`00000010`

Using our shovel operator to shift those bits to the left by a value of two, adding in zeros to fill the now empty placements, we get: 

`00001000`

This sequence now represents the value ten in base10. 

You can reverse the process either using a negative integer on the right side of the operator, or by flipping the shovel and using ">>".



Hopefully this post introduced you to some new ways to experiment with shovel. In my next post, I'll go into further detail about Ruby's metaclass feature.
