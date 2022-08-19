## How I Build NASA's Picture Of The Day using HTML, CSS, JavaScript, and NASA's API

Hi everyone,

Welcome to my blog. This post will show you how to code your first API project.

In this project, We get data from NASA and we are unable for users to choose a date and see the picture of the day.

![nasa.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1660766736821/FIrrbJHfm.gif align="left")

Link- https://nasaimage.netlify.app/

Github Link- https://github.com/shubhamsigdar1/Nasa-API

### What is API?
****
API(Application programming interface) is a Simple interface that enables us to do some complex actions.

### Think of a camera
****
The camera gives us a simple interface(i.e. on and off button) that enable us to do on and off the camera after clicking the on or off button then some complex action happened internally that turns the camera on and off.

Here, Simple interface - Button and Complex action - Turing on and off.

### Think of a Restaurant
****
Restaurants have a simple interface i.e. menu that enables me to make a request and I get the food and I don't know what complex action happens in that Kitchen.

Here, Simple interface - Menu and Complex action - Kitchen.

### The Same thing happens when we use API
****
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660098024806/iBEw3ngRm.png align="center")

Here, URL is the simple interface that enables us to make a request to the server and on the server side some complex actions happen to fulfill our request, and then the server responds with JSON.

### What is JSON?
****
It is basically an object that is coming back from the server and then we can use that object to get the data or pull the data out.

### Syntax of API 
****
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660099451503/U-iacjdWw.png align="left")
This URL actually goes to the Dog CEO Server and Dog CEO Server listening for these fetch requests, 
When it hears these fetch requests it goes and grabs data from its database and then it responds with that
data in the form of an object(i.e. JSON).

**.then(res => res.json())** // whatever we get back from the server make sure it is JSON data.


**.then(data => {
      console.log(data)
    })** // to see data inside the object


**.catch(err => {
        console.log(`error ${err}`)
    });** // If something went wrong i.e. the server is not able to respond then error message will be printed.

## How to get started?
****

**1. Install VS Code
**
https://code.visualstudio.com/download

**2. Install the extension(open in browser) in Vs Code.
**

**3. In your text editor, create a folder Pincode API and then create three separate files i.e. HTML, CSS, and JavaScript. This just basically makes your code more organized.**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660766976183/dJMt8_-Xe.png align="left")

## Let's Start working on projects
****
**First, we start from HTML files, where you can link CSS and JavaScript files using the code below:
**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660767166781/XgqHeE4yb.png align="left")

## Below is the HTML code

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660767336506/xdNjcVi_R.png align="left")

### In the above HTML code, 

**1. Code to link your HTML with the CSS file and we write it inside the head tag**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656047783937/lPETkfvkN.png align="left")

**2. Code to link your HTML with the JavaScript file and we write it inside the body tag
**
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656047921757/pk8LMK9ff.png align="left")

**3. I write class = 'hidden' in the section tag.**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660767510915/fy6Vw9ILe.png align="left")

By using class = ‘hidden’ then we can toggle that class on and off i.e. hide and show section.

****
## Below is the CSS code

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660767620260/Zy7_Vfg0r.png align="left")
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660767665602/M5HsJEgL1.png align="left")
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660767692744/pThCbp_cW.png align="left")

### In the above CSS code,

**1. To define toggle on and off to the class = 'hidden' we give property display: none;
**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660767905588/VaKbW2STR.png align="left")

**2. To add an image in a section I always use this property for the img tag and Section in which we have to put the image I apply the property "overflow: hidden;"**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660767986281/o65bUom6q.png align="left")

**3. How I design input form and button**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660768135912/mBRFaS-Hf.png align="left")
****

## Below is the JavaScript code,

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660768216145/5rPi8LeYg.png align="left")

### In the above JavaScript code

**1. We want that when we click the button of get Media(i.e. event listener that listening for clicks on that button when it hears the click it's run getFetch function. For that, we write code 
**
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660768516895/V9JVDKAnV.png align="left")

 **2. To grab input value in the DOM from the input tag, For that, we write code**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660768580717/ZrPVCNxdD.png align="left")

**3.  fetch(`https://api.nasa.gov/planetary/apod?api_key=zU71SV2z8UAS2tpSRxtx9Ii4giGUAk6QIufK4bCn&date=${choice}`
  )**

This interface or URL we use has a literal notation that enables us to plugin different Date which we choose with URL that we would want and the fetch method is used to send the request to the server and grab the request from the server.

In the above URL -> Base URL?API Key& date(i.e. we plugin) 

**4. Meaning of these two line **

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660768916464/ecGGOxY-T.png align="left")

When we grab input date then it will toggle only the image section which has class="img_section" and hide all the video section and that's why we use conditional statement.

