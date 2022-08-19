## How I Build Card Game using API and Local Storage

Hi everyone,

Welcome to my blog. This post will show you how to code your first API project using Local Storage.

In this project, I want to Build a card game called war, The way that war is played is that you are playing with someone else and you both draw cards and then compare those cards, the person with higher cards wins, and the cool things about this game is that we keep on track what is happening in the app as long as a user doesn't clear their local storage.

This game works similar to the wordle game, If I close my browser and come back I can still start playing games where I last times stops to play.

![cardgame.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1660940900917/vaVEDaivx.gif align="left")

Link- https://cardgame100devs.netlify.app/

GitHub Link- https://github.com/shubhamsigdar1/Card-Game

### What is Local Storage?
****
Local Storage is a simple method that enables us to store stuff on the user's computer across browser session

### Benefits of Local Storage
****
We can build an app and that user can come to our app to do something and after a week later come back to our app and still be able to pick up where they left off i.e. We have the ability to store stuff over a long(meaning we don’t worry about page refreshes, we don’t worry about if our users close their browsers and come back, If they come back to our application, we can store stuff that brings them back to exactly where they were).

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
    });**  // If something went wrong i.e. the server is not able to respond then error message will be printed.

## How to get started?
****

**1. Install VS Code
**
https://code.visualstudio.com/download

**2. Install the extension(open in browser) in Vs Code.
**

**3. In your text editor, create a folder Card game and then create three separate files i.e. HTML, CSS, and JavaScript. This just basically makes your code more organized.**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660942334976/s01hkatE_.png align="left")

## Let's Start working on projects
****
**First, we start from HTML files, where you can link CSS and JavaScript files using the code below:
**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660942427495/vItTgwvz7.png align="left")

## Below is the HTML code

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660942505713/8Nr3gWc-S.png align="left")

### In the above HTML code, 

**1. Code to link your HTML with the CSS file and we write it inside the head tag**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656047783937/lPETkfvkN.png align="left")

**2. Code to link your HTML with the JavaScript file and we write it inside the body tag
**
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656047921757/pk8LMK9ff.png align="left")

****
## Below is the CSS code

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660942626685/YGUNNTSrt.png align="left")
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660942650139/Z_OhCXiC8.png align="left")

### In the above CSS code,

** To add an image in a section I always use this property for the img tag and Section in which we have to put the image I apply the property "overflow: hidden;"**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660942843348/sMy056l8Q.png align="left")

****
## Below is the JavaScript code,

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660943024706/n6OYbPBya.png align="left")
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660943058140/ikMVwJGkL.png align="left")

### In the above JavaScript code

**1. fetch('https://www.deckofcardsapi.com/api/deck/new/shuffle/?deck_count=1')**

fetch method is used to send the request to the server and grab the request from the server.  This is my first fetch on page load which gets me a deck of cards then we can store the id for that deck in a global variable.

**2. Meaning of these two lines**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660943211314/MdLhBuNX8.png align="left")

In the first step, We store the id of the deck of cards that we get after fetching into local storage and then we store deck_id into the global variable deckID by using getItem from Local storage, and the reason for storing into the global variable is because we can use it anywhere in the program.

**3. We want that when we click the button of Draw Card(i.e. event listener that listening for clicks on that button when it hears the click its callback the function drawTwo with parameter deckId. For that, we write code**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660944545258/ygjMZltXV.png align="left")

**4. If the Remaining card from the deck will be 0 then I want again a new deck of 52 cards. For that, we again call the function newDeck() which fetch again a new deckId.**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660944967998/P13HnCuVj.png align="left")

**5. Suppose we get the value of the card is 'King'  Now, How we can compare this with no.?**

It is not possible to compare strings and numbers. So to make it possible we use convertToNum() which converts each string to a number.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660945270795/NH7GWwXQF.png align="left")

So the value we get after fetch, we can use convertToNum function as a call function that takes the value as an argument and passes it to convertToNum function and get back the result and store in a variable.

let player1Val = convertToNum(data.cards[0].value)
****

# Conclusion

In this tutorial, you have learned how to use API with Local storage.

The codes can be found in this <a href="https://github.com/shubhamsigdar1/Nasa-API">repository.</a>
