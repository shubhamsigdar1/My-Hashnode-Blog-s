---
title: "Get Indian City and State name From Pincode using API"
seoTitle: "API projects"
seoDescription: "Hi everyone,
Welcome to my blog. This post will show you how to code your first API project."
datePublished: Mon Aug 15 2022 07:33:55 GMT+0000 (Coordinated Universal Time)
cuid: cl6ufwhz60hyogenv1j66fpot
slug: get-indian-city-and-state-name-from-pincode-using-api
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1660548794228/eOtIqMFcw.jpg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1660548801562/fmdS-NoHR.jpg
tags: css, javascript, apis, html5, 100daysofcode

---

Hi everyone,

Welcome to my blog. This post will show you how to code your first API project.

In this project, When we write Pincode on input and click on get detail i.e. sending the request to the server, then the server responds with the city name and state name.

![pincode.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1660534441269/gRk2B1e-i.gif align="left")

Link- https://pincodeapi.netlify.app/

Github Link-  https://github.com/shubhamsigdar1/Pincode-API

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

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660534717295/LO75P4n9m.png align="left")

## Let's Start working on projects
****
**First, we start from HTML files, where you can link CSS and JavaScript files using the code below:
**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660534878777/BAcI47M46.png align="left")

## Below is the HTML code

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660535381625/YnqOq06Rc.png align="left")
### In the above HTML code, 

**1. Code to link your HTML with the CSS file and we write it inside the head tag**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656047783937/lPETkfvkN.png align="left")

**2. Code to link your HTML with the JavaScript file and we write it inside the body tag
**
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656047921757/pk8LMK9ff.png align="left")
****
## Below is the CSS code

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660535505726/3kMBmS55t.png align="left")
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660535569203/r7JlnIPcZ.png align="left")

### In the above CSS code,

** How I design input form and button**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660535805510/Wdtl23eRF.png align="left")

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660535720875/hKAbo8ZLG.png align="left")
****

## Below is the JavaScript code,

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660535928935/KGXwWIjE0.png align="left")

### In the above JavaScript code

**1. We want that when we click the button of Get Details  and then run the function get(), For that, we write code
**
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660547826066/HjPKvLhpJ.png align="left")

**2. To grab input value in the DOM from the input tag, For that, we write code**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660547915207/LmptAggDb.png align="left")

**3. fetch(`https://api.postalpincode.in/pincode/${PINCODE}`)**

This interface or URL we use has a literal notation that enables us to plugin different Pincode that we would want and the fetch method is used to send the request to the server and grab the request from the server.

**4. console.log(data[0])**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660548209781/L1HTE4hj5.png align="left")

**5. console.log(data[0].PostOffice[0])
**
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660548283040/2HyLEwRJy.png align="left")

**6. document.querySelector('.cityh2').innerText=data[0].PostOffice[0].District**

Put the District name from the Postoffice object into the .cityh2 class as text in HTML.

**7. document.querySelector('.stateh2').innerText=data[0].PostOffice[0].State**

Put the State name from the Postoffice object into the .stateh2 class as text in HTML.