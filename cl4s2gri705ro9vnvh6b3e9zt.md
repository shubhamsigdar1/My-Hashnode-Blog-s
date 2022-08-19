## How I Build Daily Music Generator Using HTML, CSS, JavaScript

**Hi everyone,**

**Welcome to my blog. In this post, I will show you how to code your first DOM project.**

In this project, We want music can be generated according to that day after we manipulate the DOM i.e. after clicking the button.

![Daily music generator.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1656051557655/uMRT42IIr.gif align="left")

**LINK**- https://dailymusicgenerator.netlify.app/

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

**3. In your text editor, create a folder Daily Music Generator and then create three separate files i.e. HTML, CSS, and JavaScript. This just basically makes your code more organized.**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656045531577/5kpDLnbdI.png align="left")


## Let's Start working on projects
****
**First, we start from HTML files, where you can link CSS and JavaScript files using the code below:
**
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656046565744/r2DHZ-f9B.png align="left")

****

## Below is the HTML code

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656046767680/v1tQhO1xP.png align="left")

### In the above HTML code, 
**1. Code to link your HTML with the CSS file and we write it inside the head tag**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656047783937/lPETkfvkN.png align="left")

**2. Code to link your HTML with the JavaScript file and we write it inside the body tag
**
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656047921757/pk8LMK9ff.png align="left")

**3. we write class = 'hidden' in the section tag.**
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656046995119/l3w56no8y.png align="left") By using class = ‘hidden’ then we can toggle that class on and off i.e. hide and show section. 

**4. You can copy and paste this embedded code inside the class = 'hidden' section from Youtube **

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656047479386/tV9JKNbbw.png align="left")

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656047644959/OskYSTzHA.png align="left")
****

## Below is the CSS code

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656048099615/ScRUcSNY5.png align="left")

### In the above CSS code,

** To define toggle on and off to the class = 'hidden'  we give property display: none;**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656048397430/F7lgr6nuC.png align="left")
****

## Below is the JavaScript code
 
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656048573932/J1gJhTVKg.png align="left")

### In the above JavaScript code,

**1. We want that  when we click the button and then run the function findMusic(), For that, we write code**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656048799061/_uQoaAetF.png align="left")

**2. When the button is clicked what first thing function findMusic() needs to figure out?**

**what day it actually is by using the built-in object function Date**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656049091135/OAFqBInqe.png align="left")

**The Date object is an inbuilt datatype of JavaScript language. It is used to work with dates and times. The Date object is created by using new keyword, i.e. new Date().**

> const d = new Date();-> **It means grab current date**

 > let day = d.getDay() -> **Hey function give me back what day in the week and it return value from 0 to 6**  
**0 means→ sunday and 6 → saturday i.e. grab numerical day from 0 to 6**

**But I want Today is Sunday rather than value 0?**

**So, That's why we create an array**

> const weekday = ['sunday', 'monday', 'Tuesday', 'wednesday', 'Thursday', 'Friday', 'Saturday']

> const d = new Date( ); 

> let day = weekday[d.getDay()] //weekday[0]


**3. We want that the output comes from variable day(i.e. let day = weekday[d.getDay()]) 
assigned to HTML tag h2 which has class = 'todayIs' So for that we use innerText **

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656050213224/3BlLX4tz1.png align="left")

**4. **![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656050582747/-YquvaSeb.png align="left")

**Its means HTML element with an id = 'sunday'  look at the class and toggle the hidden class from whatever state it is in i.e. ON and OFF **
