+++
categories = ['technical']
date = '2022-01-18T20:46:21+02:00'
draft = false
title = 'Antipattern: Lava Flow'
+++

Today I would like to talk to you about the antipattern "Lava Flow" (also known as "Dead code"). An antipattern that unfortunately I have encountered in some projects I have worked on.

![Presentation image with a volcano icon and the text Lava flow antipattern](imgs/lava_flow_antipattern_card.png)

This antipattern usually occurs in projects that are initially created as prototypes, research software, or as part of a hackathon, but later become operational software and are taken to production.

The reason behind the name "Lava Flow" is simple. Initially, the software is developed with very vague or non-existent documentation, trying several solutions to implement the program's functions, either due to very limited time or because developers try different ways to reach a solution. That initial code, which is part of the early versions, ends up being dragged along, and when the time comes to refactor it, it is too late. The technical debt accumulated is so immense that no one on the team knows if a refactor could cause more problems than it solves.

This antipattern becomes even more evident when the developers who started the project are no longer part of it. If you haven’t had to go through this, imagine what it is like to reverse engineer a project with thousands of poorly documented lines full of spaghetti code.

The solution to this antipattern once it is present in the code is quite complex. Without a doubt, the best approach would be to review, document, and replace the useless code as much as possible. But since there usually isn’t unlimited time to do this, there are some tools (for example Sonarqube) that can help us perform automatic static code analysis. This way, at least we can identify the most critical points and prioritize those changes.

To prevent this from happening in our projects, we should always try to document the code from the start of the project and keep it relatively "clean." Even if it’s a project you do to try something out or as a hobby. You never know if in the future you will use it to do something more complex.

> 🖼️ The Eruption of Vesuvius. 1771. Pierre-Jacques Volaire. 
