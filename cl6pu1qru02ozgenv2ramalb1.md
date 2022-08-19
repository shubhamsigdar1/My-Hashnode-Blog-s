## How I Build Dog Generator using HTML, CSS, JavaScript, and  Dog CEO API.

Hi everyone,

Welcome to my blog. In this post, I will show you how to code your first API project.

In this project, When we choose a dog breed from a select option i.e. sending the request to the server,
then the server responds with an image of a dog of that breed.

![dog breed API.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1660096278001/frg-govOA.gif align="left")

Link- https://dogbreedapi100devs.netlify.app/

Github Link- https://github.com/shubhamsigdar1/Dog-breed-API

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

**3. In your text editor, create a folder Dog-breed-API and then create three separate files i.e. HTML, CSS, and JavaScript. This just basically makes your code more organized.**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660100114033/_oFgavpxk.png align="left")

## Let's Start working on projects
****
**First, we start from HTML files, where you can link CSS and JavaScript files using the code below:
**
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660100338552/EcPX-PEKw.png align="left")

## Below is the HTML code

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660100451605/Kh_evNZ0i.png align="left")

### In the above HTML code, 
**1. Code to link your HTML with the CSS file and we write it inside the head tag**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656047783937/lPETkfvkN.png align="left")

**2. Code to link your HTML with the JavaScript file and we write it inside the body tag
**
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656047921757/pk8LMK9ff.png align="left")
****
## Below is the CSS code
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660100595473/wm-A9Tu9F.png align="left")![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660100635053/NBB7FInQN.png align="left")

### In the above CSS code,
**1. How I add images in a section?**

I use always this property for img tag and Section in which we have to put the image I apply property
"overflow: hidden;"

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660101167220/H3KvfDEPw.png align="left")

**2. How I add Background images?**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660101342797/K-LYDTrYI.png align="left")
****
## Below is the JavaScript code

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660101423081/sRe7oaatL.png align="left")

### In the above JavaScript code,

**1. fetch('https://dog.ceo/api/breeds/list/all') 
**

fetch method is used to send the request to the server and grab the request from the server.


**2. console.log(data)**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660102051444/edi2uSGpY.png align="left")
We get objects containing property messages and status.


**3. const breedsObject = data.message;**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660102270996/o11pmgqCt.png align="left")
To grab value of the message from the object data we write data.message.


**4. const breedsArray = Object.keys(breedsObject)**

Object.keys() method returns an array of a given object's.

To Understand more about how object.keys() work, I refer MDN 
(https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/keys)

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660102649660/RQj2wj_le.png align="left")


**5. How to create an option element in the DOM and after that insert it into the select tag?**

- Step1:- Create an empty option element using document.createElement('option').
- Step2:- Then set its attributes like (value, class, etc.)
- Step3:- Finally, insert it into the document.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660103785133/7FG_ATsmH.png align="left")

**6. We want that when we change the option of dog breed in the select tag and then run the function(), For that, we write code**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660103989021/zUDoDDIas.png align="left")


**7. let  url = `https://dog.ceo/api/breed/${event.target.value}/images/random`**

This interface or URL we use has a query parameter that enables us to plugin different dog breeds that we would want.