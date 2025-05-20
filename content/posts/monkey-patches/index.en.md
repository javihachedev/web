+++
categories = ['technical']
date = '2021-11-24T00:00:00+00:00'
draft = false
title = 'Monkey patches'
+++

Do you know what monkey patches are? 🐒

You’ve probably seen them before or even implemented them without realizing it. In this post, I’ll clarify this concept to help you introduce *hotfixes* or patches into your code.

A *monkey patch* is a term used for changes or patches applied at runtime to functionalities that are already implemented in your code—or in external libraries or components.

This technique is usually used to temporarily modify specific logic and fix isolated cases.

Here’s an example in JavaScript:

```js
// Create a class with a defined behaviour
class Monkey {
  constructor(name) {
    this.name = name;
  }

  sayMyName() {
    console.log(this.name);
  }
}

// Create a couple of Monkey instances
let monkeyAndrew = new Monkey("Andrew");
let monkeyRyan = new Monkey("Ryan");

// Monkey Patch the method "sayMyName" 
// for the instance monkeyAndrew
monkeyAndrew.sayMyName = () => {
  console.log(monkeyAndrew.name + " I");
};

// Call to the method "sayMyName"
monkeyAndrew.sayMyName();
monkeyRyan.sayMyName();

When you run it, you’ll get the following:

Andrew I  
Ryan
```

As you can see, what we’ve done is apply a monkey patch to the monkeyAndrew instance of our Monkey class. This way, the behavioral change only affects that specific object, not the others.

Monkey patches can also be applied to external libraries or components if the language or framework allows it. For example, in Python:

```js
>>> import math

# Print PI
>>> math.pi
3.141592653589793

# Monkey patch PI and print it
>>> math.pi = 3.1
>>> math.pi
3.1
```

This practice can be really useful in specific cases where we want to change a default component's behavior. However, it’s generally not advisable to apply this kind of patch. Introducing monkey patches creates unexpected logic that may lead to hard-to-find bugs or strange behavior down the line.

There’s some valid use for monkey patches in unit testing. For example, when creating a stub or mock for a method to return data without calling the real method. In other cases, there are probably better solutions, like extending the class or function that needs the new behavior.

> 🖼️ Jacques de Sève.