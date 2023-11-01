---
layout: post
title: "Entity Framework Reflection"
author:
- Jacob Collier-Tenison
---
Like the other Razor Pages tutorials, the Entity Framework Tutorial made it quite easy to set up all the pages. By creating a few simple pages and running commands, I could create all of the pages that I needed. Even adding the filtering and search was quite simple based on the tutorial. Really, the only part that was more difficult was planning it out. 

You have to have a good understanding of how your data is organized and how your tables will be connected to build everything out. Specifically, you have to know what keys will connect the tables so that you can create the tables properly. However, it is not difficult to create the tables once you know this. Even pulling information from other tables for display is pretty simple, as long as you know what you should be looking for. 

After going through this tutorial, I feel prepared to create our team project. Our project model is actually a bit simpler than the one in the tutorial. We have three tables: artwork, medium, and artist. The artwork table will simply need to hold a medium and artist ID for our model to function. This is a simple relationship that will not require us to create additional tables, such as enrollments. It will be more like a course being assigned to a department for each case. We will also add search like we saw in the tutorial to allow people to search through the gallery. 
