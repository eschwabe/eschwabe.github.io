---
layout: post
title:  "Experiments with WebGL"
date:   2016-05-01 18:00:00 -0800
categories: classes
tags: coursera classes webgl
comments: true
---

Coursera classes can be a great tool for learning new technologies or improving existing skills. Last year (Summer 2015), I took a course on WebGL to learn a bit more about web browser technology and refresh my knowledge of basic 3D rendering. The last time I worked with graphics APIs was a game development certificate course back in 2010 that used DirectX 9. I will discuss a bit about the assignments, the course content, and my overall impressions of the class.

## The Results

Let's start with the final product. Demos are always fun to show. :) The page renders a simple 3D scene with a grid and a set of objects (starting with a single sphere). The scene may be observed using the camera which starts out as automatically rotating around the grid. Additional objects may be added to the scene and their position, rotation, and scale controlled. Lastly, the environment has two simple spotlights whose position can be manipulated. Try it out! 

#### **[WebGL Example](/graphics-webgl/assignment5/)**

![Example]({{ site.baseurl }}/images/2016-05-01-webgl-example.png)

The class had us implement several intermediate steps before the final assignment. The other assignments provided opportunities to learn more about the computations involved with 3D graphics and the WebGL API. You can also try out those here.

**[WebGL Assignments](/graphics-webgl/)**

- Assignment 1: Tessellation and Twist
- Assignment 2: Painting with the Mouse
- Assignment 3: Geometric CAD
- Assignment 4: Adding Lighting
- Assignment 5: Texture Mapping

## The Content

The course itself covered the major topics required for 3D rendering and using WebGL. The class focuses on WebGL due to the fact that it is the primary platform independent implementation of a 3D graphics API. The high-level course outline is listed below. You can find out more on **[Coursera](https://www.coursera.org/)** (course no longer offered).

- Week 1: Introduction and Background
- Week 2: WebGL
- Week 3: The Open GL Shading Language and Interaction
- Week 4: Displaying Geometry in WebGL
- Week 5: Transformations 
- Week 6: Viewing in WebGL
- Week 7: Lighting, Shading and Texture Mapping
- Week 8: WebGL Texture Mapping
- Week 9: Using the GPU
- Week: 10: Render-to-Texture Applications


## Course Review

Overall, I felt the class was a decent review of 3D graphics programming. The assignments and topics covered the most important aspects of using WebGL and turned out to be a great refresher for my knowledge. My main issue with the course would be the lectures. The audio and video quality was poor and the instructor did not explain topics thoroughly. I generally had to go back through the slides or lookup information through other sources to understand the topic. With that said, I would still recommend the course if you have an interest in WebGL.

I may expand on this post in the future to use as reference. Some of the intricacies of 3D programming (such as the model, view, and projection matrices) are easy to forget.