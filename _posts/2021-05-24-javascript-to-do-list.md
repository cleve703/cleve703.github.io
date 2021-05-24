---
layout: post
title: JavaScript To-Do List
date: 2021-05-24 0:33:12 -0500
tags: [html-css, javascript]
image: to-do-screenshot.png
---
My most recent project of the JavaScript curriculum at [theOdinProject](http://theodinproject.com), was to create an app to manage a To-do list. This project required a lot building HTML elements through JavaScript, and it also showcased my ability to organize my code into different modules in separate files. Another new concept introduced in this project was saving data via localStorage.

At first, localStorage was a fairly foreign concept to me, and I was unsure of any distinction between it and cookies. As it turns out, there are some subtle yet significant differences between localStorage and cookies. Cookies, which predate localStorage, are stored as separate files on the end user's computer. Additionally, they must be defined with specific criteria such as an expiration date. In contrast, localStorage has no expiration date, and it is managed within a browser's cache. Therefore, a user can clear out all of their cookie data and still have access to the data in localStorage. With that said, localStorage would be lost when the user clears out his/her cache.

With an understanding of the general concept of localStorage, let's discuss the nuts and bolts of implementing it in a project such as this one. Like many things in JavaScript, use of localStorage is not as straightforward as one might like - it requires that you convert your object data to a more simple format. I utilized a method of converting the data to JSON for storage, and parsing it back into a JavaScript array of hashes to be processed by the application. Here's an excerpt of my code that shows how I turned JavaScript objects into JSON:

```
  function saveToLocalStorage() {
    localStorage.setItem('allProjects', JSON.stringify(allProjects));
    localStorage.setItem('allTasks', JSON.stringify(allTasks));
    localStorage.setItem('projectCounter', JSON.stringify(projectCounter));
    localStorage.setItem('taskCounter', JSON.stringify(taskCounter));
  }```

And this is how I converted JSON back into JavaScript objects:

```
  function initProjects() {
    var localAllProjects = localStorage.getItem('allProjects');
    console.log(localAllProjects);
    var localAllTasks = localStorage.getItem('allTasks');
    console.log(localAllTasks);
    var localProjectCounter = localStorage.getItem('projectCounter');
    var localTaskCounter = localStorage.getItem('taskCounter');
    
    if ((localAllProjects !== undefined) && (localAllProjects !== null)) {allProjects = JSON.parse(localAllProjects)};
    if ((localAllTasks !== undefined) && (localAllTasks !== null)) {allTasks = JSON.parse(localAllTasks)};
    if ((localProjectCounter !== undefined) && (localProjectCounter !== null)) {projectCounter = JSON.parse(localProjectCounter)};
    if ((localTaskCounter !== undefined) && (localTaskCounter !== null)) {taskCounter = JSON.parse(localTaskCounter)};

    if (allProjects.length == 0) {
      createProject('Welcome');
    }
}
```


My To-do list was a lot of hard work, but it was a rewarding learning experience. I really enjoyed using JavaScript to modify objects based on user input and ultimately use CSS to reflect the user changes in a visual manner. For example, I used JavaScript to detect when the user clicks on the checkbox, and modified the "complete" property of the task. Then, I caused much of the page to regenerate and detect the completion status of the checkbox to determine whether to place a check in the checkbox. Additionally, the JavaScript modified some of the HTML elements' classes so that CSS in turn could apply a strikethrough effect on the task title and description.

Here are some links to check out my project:
* [CodingCop's To-do List App](https://codingcop.com/todo/dist/index.html)
* [CodingCop's To-do List Code at GitHub](https://github.com/cleve703/todo)

I'm starting to get the hang of using JavaScript, and am already thinking of ways I can harness its power to streamline and organize data at work. Please comment with any ideas you  have about how JavaScript can be used to improve productivity in new ways in your work or personal life.