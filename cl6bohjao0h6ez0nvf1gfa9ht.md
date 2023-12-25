---
title: "How I build  DOM manipulation project  using HTML, CSS3, JavaScript"
seoTitle: "DOM manipulation javascript project"
seoDescription: "How I build "Class, Weekend, Boring DOM manipulation project " using HTML, CSS3, JavaScript"
datePublished: Tue Aug 02 2022 04:26:36 GMT+0000 (Coordinated Universal Time)
cuid: cl6bohjao0h6ez0nvf1gfa9ht
slug: how-i-build-dom-manipulation-project-using-html-css3-javascript
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1659414273181/6aZOW11Mu.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1659414331239/4PlC5KxGG.png
tags: css, javascript, opensource, html5, 100daysofcode

---

**Hi everyone,**

**Welcome to my blog. In this project, I will show you how to code your first DOM project.**

In this project, we put the day in the week in the input and after clicking the Button based on the input DOM will be manipulated

![class,weekend,.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1659411648755/n55sW9Boj.gif align="left")

**LINK**- https://class-weekend-boring-day.netlify.app/

**GitHub**- https://github.com/shubhamsigdar1/Class-Weekend-Boring

### What is DOM?
****
When we do rendering/Painting on our HTML and CSS in a browser i.e. make some changes and as we refresh our webpage all those changes are gone i.e. we re-rendered or repainted our HTML and CSS files i.e. called DOM

### How we can add behavior and interaction to DOM so that we can manipulate the DOM?
****
**We use JavaScript to manipulate the DOM**

> **Note:-When we manipulate the DOM, We do not manipulate with actual HTML, CSS file**

## How to get started?
****

**1. Install VS Code
**
https://code.visualstudio.com/download

**2. Install the extension(open in browser) in Vs Code.
**

**3. In your text editor, create a folder Daily Music Generator and then create three separate files i.e. HTML, CSS, and JavaScript. This makes your code more organized.**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657752296168/KPwXgKXuW.png align="left")

## Let's Start working on projects
****
**First, we start from HTML files, where you can link CSS and JavaScript files using the code below:
**
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656046565744/r2DHZ-f9B.png align="left")

****

## Below is the HTML code

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659411941292/j2LPKk_pH.png align="left")

### In the above HTML code, 

**1. Code to link your HTML with the CSS file and we write it inside the head tag**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656047783937/lPETkfvkN.png align="left")

**2. Code to link your HTML with the JavaScript file and we write it inside the body tag
**
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656047921757/pk8LMK9ff.png align="left")

**3. we write class = 'hidden' in the section tag.**
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659412103725/f_GOF0ur9.png align="left")
By using class = ‘hidden’ then we can toggle that class on and off i.e. hide and show section. 

## Below is the CSS code

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659412220354/QdgqLVRAw.png align="left")
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659412252659/kSXE1gd9u.png align="left")
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659412273420/h3yMWGtjM.png align="left")

### In the above CSS code,

**1. To define toggle on and off to the class = 'hidden'  we give property display: none;**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656048397430/F7lgr6nuC.png align="left")

**2.  To add an image in a section I always use this property for the img tag and Section in which we have to put the image I apply the property "overflow: hidden;"**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659412565302/XQ3APgPzl.png align="left")

## Below is the JavaScript code

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659412767831/g8Yf87GQJ5.png align="left")

### In the above JavaScript code,

**1. We want that when we click the check button and then run the function(), For that, we write code**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659413201250/3YF-mzfDW.png align="left")

**2. To grab input value in the DOM from the input tag, For that, we write code**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659413407799/idSO-52BU.png align="left")

**3. How to create an image element in the DOM and after that insert it into the section? **

- Create an empty img element using document.createElement() method.
- Then set its attributes like (src, height, width, alt, title, etc).
- Finally, insert it into the document.
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659413713272/hztZ-tZJL.png align="left")

**4. Meaning of these three lines**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659414174942/ePOvwCIoA.png align="left")

When we grab input Tuesday and Thursday then it will toggle only the section which has id #imagesection1 and hide all the other two section
