---
layout: post
title: TheNextWeb Clone Project and the Pitfalls of CSS Background Images
date: 2020-10-04 08:09:12 -0500
tags: [html-css]
image: thenextweb.png
---
I recently completed a clone of [TheNextWeb](http://thenextweb.com), a news site that targets the web development industry. This project tested my ability to use media queries and CSS Grid. Media queries are a key component of responsive web design, which is just a fancy term to describe websites that look good on all devices (phones, tablets and computers.) So, when you visit either the original website, or my [clone of it](http://htmlpreview.github.io/?https://github.com/cleve703/thenextweb/blob/master/index.html), you'll see that the layout of the website changes as you resize your browser window. On smaller screens, the website displays largely in a single column, but as the screen gets wider, content is shown in multiple columns.

After hours of coding to produce this result, I pushed my project to [GitHub](https://github.com/cleve703/thenextweb) and soon discovered that some of the images were not displaying as they had when viewing the site directly from the hard drive of my laptop. I quickly figured out that the images not displaying were the ones added to page as background images. (I did this because I wanted to modify some of images through CSS to have a gradient effect, and others I wanted to combine a vector image with a CSS shape to make an icon.) But why what was causing this to happen?

After several Google searches, I turned to my peers at [theOdinProject](https://theodinproject.com)'s [Discord](https://discord.com) channel for HTML/CSS. There, I learned that CSS background images do not work with relative paths from a remote browser. In other words, if the CSS file contains a line of 

```background-image: url("./img/example.jpg")```

 this would work fine if the file is in the corresponding folder on the computer accessing the html file. However, if the html file is hosted online, this does not work -- the CSS item would have to show the absolute path to the file, such as
 
  ```background-image: url("https://raw.githubusercontent.com/cleve703/thenextweb/master/img/cat-date.jpg")```.

I'm now hard at work on my next project, a clone of [Newsweek.com](https://newsweek.com), and I look forward to reporting my experience in a future blog post. Please leave a comment with anything interesting you learned while building this project, or any other questions or comments you might have.