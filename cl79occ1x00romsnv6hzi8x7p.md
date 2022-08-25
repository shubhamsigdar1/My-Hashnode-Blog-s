## How I Build Book Tracker App using API and Local Storage

Hi everyone,

Welcome to my blog. This post will show you how to code your first API project using Local Storage.

In this project, I want to Build a Book Tracker App in which we are going to use an API that wants our users to enter an ISBN no. of Books that they have read and then the server responds with the Title of the Book and then we are gonna store that title of the Book into the Local Storage. So that whenever the user comes back they can see all of the books they have read over time.


![booktracker.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1661464180089/vsHUj4S3F.gif align="left")

Link- https://booktracker100devs.netlify.app/

GitHub Link- https://github.com/shubhamsigdar1/Book-Tracker-Application

### What is Local Storage?
****
Local Storage is a simple method that enables us to store stuff on the user's computer across browser session

### Benefits of Local Storage
****
We can build an app and that user can come to our app to do something and after a week later come back to our app and still be able to pick up where they left off i.e. We can store stuff over a long(meaning we don’t worry about page refreshes, we don’t worry about if our users close their browsers and come back, If they come back to our application, we can store stuff that brings them back to exactly where they were).

### How does Local Storage work?
****

Without using any Database, Still, We could be able to store data on a User-machine that we can use later and we don’t have access to the database or anything yet so local storage is a great way to have some that stick around even if they leave the browser and come back.

**- How to put the item in Local Storage in user-machine **

LocalStorage.setItem(’bestFriend’,’Bob’)
   
**-  How to get the item from Local Storage from user-machine**

LocalStorage.getItem(’bestFriend’)

output→ ‘Bob’

**- How to remove the item from Local Storage**

LocalStorage.removeItem(’bestFriend’)

output→ undefined

**- How we can clear all the things in Local Storage**

LocalStorage.clear()



### Steps to see local storage in the browser
****
Inspect —> Application —> Local Storage —> Link.

### What is API?
****
API(Application programming interface) is a Simple interface that enables us to do some complex actions.

### Think of a camera
****
The camera gives us a simple interface(i.e. on and off button) that enable us to do on and off the camera after clicking the on or off button then some complex action happened internally that turns the camera on and off.

Here, Simple interface - Button and Complex action - Turing on and off.

### Think of a Restaurant
****
Restaurants have a simple interface i.e. menu that enables me to make a request and get the food and I don't know what complex action happens in that Kitchen.

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
    });**  // If something went wrong i.e. the server is not able to respond then an error message will be printed.

## How to get started?
****

**1. Install VS Code
**
https://code.visualstudio.com/download

**2. Install the extension(open in browser) in Vs Code.
**

**3. In your text editor, create a folder Card game and then create three separate files i.e. HTML, CSS, and JavaScript. This just basically makes your code more organized.**


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1661464393797/y3Pt1CKex.png align="left")

## Let's Start working on projects
****
**First, we start from HTML files, where you can link CSS and JavaScript files using the code below:
**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1661464477276/2kdunOTWb.png align="left")

## Below is the HTML code

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1661464547596/72NXc2mc2.png align="left")

### In the above HTML code, 

**1. Code to link your HTML with the CSS file and we write it inside the head tag**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656047783937/lPETkfvkN.png align="left")

**2. Code to link your HTML with the JavaScript file and we write it inside the body tag
**
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656047921757/pk8LMK9ff.png align="left")

****

## Below is the CSS code

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1661464813102/yJSdQrNOx.png align="left")
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1661464834209/b3Ihg39p1.png align="left")
****
## Below is the JavaScript code,

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1661464992997/QqpyRbB9N.png align="left")
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1661465016177/rSMTTXn5G.png align="left")

### In the above JavaScript code

**1. We want that when we click the button and then run the function getFetch(), For that, we write code**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1661465509055/73YYm7ix3.png align="left")

**2. To grab input value in the DOM from the input tag, For that, we write code**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1661465744800/i9JYec8--.png align="left")

**3. fetch(`https://openlibrary.org/isbn/${choice}.json`)**

This interface or URL we use has a template notation that enables us to plugin different ISBN no. that we would want and the fetch method is used to send the request to the server and grab the request from the server.

**4. How to create a list element in the DOM and after that insert it into the order list tag?**


- Step1:- Create an empty list element using document.createElement('li').

- Step2:- Then add text to li

- Step3:- Finally, insert it into the document.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1661466882623/UgWqHreTP.png align="left")

**5. Difference between JSON.stringify and JSON.parse**

The JSON.stringify() method converts a JavaScript object or value to a JSON string and The JSON.parse() method parses a JSON string and convert into the JavaScript value or object described by the string.

**6. Meaning of these two lines of code**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1661468173168/NIs5c9en7.png align="left")

if you do not enter any value in the input then run these codes.

**7. Meaning of these two lines of code**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1661468423376/dZ5t-T19E.png align="left")

if you enter an ISBN no. of a book whose title of book is already stored in local storage or a list then run this code

**8.  localStorage.setItem('books',JSON.stringify(localListItem))**

we store the title of the book which we get after fetching from API into local storage as an array element and the name of the array is localListItem and after that, we convert the array to a string using JSON.stringify because in local storage we can only store data as a string.

**9. Meaning of these codes**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1661469118354/X35_F77er.png align="left")

We want that when we refresh our page we can able to get all items back to exactly where they were.

**10. var localListItem=JSON.parse(localStorage.getItem('books')||"[]");**

To get items from localStorage we use localStorage.getItem('books') and if there is no item in local storage we get an empty array and JSON parse converts JSON string to normal javascript value.

****
# Conclusion
In this tutorial, you have learned how to use API with Local storage.

The codes can be found in this <a href="https://github.com/shubhamsigdar1/Book-Tracker-Application">repository.</a>




