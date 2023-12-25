---
title: "Background Picker Using HTML, CSS, JavaScript"
datePublished: Mon Jul 11 2022 22:56:23 GMT+0000 (Coordinated Universal Time)
cuid: cl5hcfz9a01vqt4nv7oxu85zf
slug: background-picker-using-html-css-javascript
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1657520902383/vbJrEH_Yn.png
tags: css, javascript, opensource, html5, 100daysofcode

---

Hi everyone,

Welcome to my blog. In this post, I will show you how to code your first DOM project.

In this project, We want the Background Image will be changed after we manipulate the DOM i.e. after clicking time of the day.**

![Background picker.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1657521356600/QuoODOK4v.gif align="left")

Link- https://time-of-the-day-picker.netlify.app/

Github Link- https://github.com/shubhamsigdar1/Background-Picker

### What is DOM?
****
When we do rendering/Painting on our HTML and CSS in a browser i.e. make some changes and as we refresh our webpage all those changes are gone i.e. we re-rendered or repainted our HTML and CSS files i.e. called DOM

### How we can add behavior and interaction to DOM so that we can manipulate the DOM?
****
**We use the JavaScript to manipulate the DOM**

> **Note:-When we manipulate the DOM, We do not manipulate with actual HTML, CSS file**

## How to get started?
****

**1. Install VS Code
**
https://code.visualstudio.com/download

**2. Install the extension(open in browser) in Vs Code.
**

**3. In your text editor, create a folder Background-Picker and then create three separate files i.e. HTML, CSS, and JavaScript. This just basically makes your code more organized.**

![hashnode 22.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657521626380/IpAgWfxXX.png align="left")

## Resources
****
**1. Images from this website:-** https://www.freepik.com/

**2. fonts from this website :-** https://fonts.google.com/specimen/Kaushan+Script


## Let's Start working on projects
****
**First, we start from HTML files, where you can link CSS and JavaScript files using the code below:
**

![Image 1.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657575872168/J91nM3-Qv.png align="left")
****

## Below is the HTML code

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657577215016/KuccWUB2b.png align="left")

### In the above HTML code, 
**1. Code to link your HTML with the CSS file and we write it inside the head tag**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656047783937/lPETkfvkN.png align="left")

**2. Code to link your HTML with the JavaScript file and we write it inside the body tag
**
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656047921757/pk8LMK9ff.png align="left")
****

## Below is the CSS code

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657577459762/Yzql9R_LD.png align="left")![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657577504634/MitJlCvt1.png align="left")

### In the above CSS code,

### 1. How I do this portion using flexbox?

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657577818789/Rcmr8Z9c2.png align="left")
    
 

### I give parent section two property display: flex; and flex-wrap : wrap; 

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657578526995/bxmntH_My.png align="left")
    
### display: flex; 
 **Whenever we want to use flexbox, We have to apply  display: flex inside the parent container**

### flex-wrap : wrap;
**This property helps you set the number of flex-items you want in a line or row.**
 
### 2. How I add images in a section?


**I use always this property for img tag and Section in which we have to put the image I apply property
"overflow: hidden;"**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657579172159/B7janT9ix.png align="left")
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657579295525/nkQCbtAPq.png align="left")

## Below is the JavaScript code

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657579519129/fyqRi5ql0.png align="left")

### In the above JavaScript code,

**1. We want that  when we click the images of the day and then run the function morn(), For that, we write code**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657579620630/ITgJ5A0qO.png align="left")

**2. When the button is clicked on morning image what first thing function morn() needs to figure out?**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657579985423/125pozhu0.png align="left")

**3. How to add background image in DOM?**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657581644266/JCuWeZSr_.png align="left")

 **`./` starts in the same folder as the file that is making the reference 
you could also just do `img/evening.jpg`
**

*`../` - goes up one level
*

**`/` would start at the root (your C: drive or whatever drive you are on locally... when you host, it starts at www.yoursite.com/)
**
