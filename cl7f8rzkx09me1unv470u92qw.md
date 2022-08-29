## How I made a Tic-tac-toe Game using JavaScript

Hi everyone,

Welcome to my blog. This post will show you how to code your first DOM manipulation project.

In this project, We are going to make Tic-tac-toe Game using HTML, CSS, and JavaScript.

![tictactoe.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1661572307950/49KT0dIta.gif align="left")

LINK- https://tictactoe100devs.netlify.app/

GitHub- https://github.com/shubhamsigdar1/Tic-Tac-Toe-Game-100Devs


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

**3. In your text editor, create a folder Tic-tac-toe and then create three separate files i.e. HTML, CSS, and JavaScript. This makes your code more organized.**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1661573582208/N1hd1U1wX.png align="left")

## Let's Start working on projects
****
**First, we start from HTML files, where you can link CSS and JavaScript files using the code below:
**
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1661573816012/poaAZqWcW0.png align="left")
****

## Below is the HTML code

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1661573951239/Ehnx0W8zd.png align="left")

### In the above HTML code, 

**1. Code to link your HTML with the CSS file and we write it inside the head tag**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656047783937/lPETkfvkN.png align="left")

**2. Code to link your HTML with the JavaScript file and we write it inside the body tag
**
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656047921757/pk8LMK9ff.png align="left")

****
## Below is the CSS code

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1661800375766/foUu5O1MF.png align="left")
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1661800402836/0Oqbc3jVp.png align="left")

****
## Below is the JavaScript code,

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1661801093828/aFx0T_TE0.png align="left")
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1661801128909/_V_ATOU6I.png align="left")
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1661801159206/Ga4uZBj8u.png align="left")
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1661801184615/nTaRcXE8b.png align="left")

### In the above JavaScript code

**1. let tiles = Array.from(document.querySelectorAll('.tile'))**

Array.from() method returns an array from all the elements of the class of tile and stored in variable name tiles. 

When you console log(tiles) you will get 
[div.tile, div.tile, div.tile, div.tile, div.tile, div.tile, div.tile, div.tile, div.tile]

**2. tiles.forEach(tile => tile.addEventListener('click', toggleX)) **

add event listener to all board tiles

**3. Meaning of these lines of code**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1661804531934/hMap0B8Wy.png align="left")

**if(click.target.classList.contains('o'))** =>  means to look at the user actually click on and if the user click on has already contained the class 'o' then alert 'Please choose another tile'

else **click.target.classList.add('x')** => means to look at the user actually click on then add class 'x' on particular div of class 'tile' where user will actually click

**player1State = tiles.map((t, i) =>  t.classList.contains('x') ? i : 'skip').filter((e, i) => e !== 'skip')**

meaning of this line is to assign tiles to player1State selections i.e. For ex:- if player1 clicks first time suppose on the first div of class 'tile' and it will also checks div contains class 'x' then it will return [0]  i.e. player1State = [0]
and if player1 clicks again on next turn suppose on the third div of class 'tile' and also checks div contains class 'x' then it will return [0,3]  i.e. player1State = [0,3]

if you didn't understand now also then try to console.log(player1State)

**4. Difference between some method and every method in javascript**

```
const p1 = winCons.some(combo => {
    return combo.every(e => player1State.includes(e))
  })
```
The Array.some() method in JavaScript is used to check whether at least one of the elements of the array satisfies the given condition or not. The only difference is that the some() method will return true if any predicate is true while every() method will return true if all predicates are true. 

**5. Meaning of these lines of code**
```
if (!checkWin()){      
        //sets delay for showing next players turn
      setTimeout(function(){h2.innerText = `Player 1's Turn`},250)
        //switch counter to player 1 turn
      turn = 1
    }
```

it runs only if checkWin() return false

**6. Meaning of these lines of code**

```
if(p1){
    // alert('Player 1 wins!')
    h2.innerText = `Player 1 Wins`
    //add event listener to all board tiles 
  tiles.forEach(tile => tile.removeEventListener('click', toggleX))
    return true
  }
```
if player1 wins then put in h2 element `Player 1 Wins` as text in HTML and after that remove event listener to all board tiles

# Conclusion

In this tutorial, you have learned how to use DOM manipulation.

The codes can be found in this <a href="https://github.com/shubhamsigdar1/Tic-Tac-Toe-Game-100Devs">repository</a> and please go through each line of the code and if you feel you didn't understand any line of the code then come and read my blog again or comment below.