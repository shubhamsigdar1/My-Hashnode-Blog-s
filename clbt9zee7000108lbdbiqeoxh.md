---
title: "How to Accept User Input On Game Board Of Wordle using JavaScript"
seoTitle: "Wordle game"
seoDescription: "Welcome to my blog. This post will show you How to Accept User Input in the right place or when the user key is pressed was Enter or Backspace"
datePublished: Wed Dec 14 2022 11:17:57 GMT+0000 (Coordinated Universal Time)
cuid: clbt9zee7000108lbdbiqeoxh
slug: how-to-accept-user-input-on-game-board-of-wordle-using-javascript
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1671362140290/Myx51aaYz.png
tags: css, javascript, html5, blogswithcc, wemakedevs

---

Hi everyone,

Welcome to my blog. This post will show you **How to Accept User Input in the right place or when the user key is** pressed was Enter or Backspace, then go to the next line or delete one letter from the current row **on the wordle board using javascript.**

In this project, I will show you when u press a key on the keyboard, we want to place that key in the right place on the board. You're going to accomplish this by listening to the keyup event. When u press a key, you want to find out what that key was. If the key was a single letter, you want to put it in the right spot on the board.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671354997798/vFrF0Tpon.gif align="center")

##   
Let's see the **JavaScript code**

**Caution:-** Before you jump into this Blog...Please read my previous Blog([LINK](https://shubhamsigdar.hashnode.dev/how-i-create-the-game-board65-of-wordle-using-javascript))

```javascript
//current row letter stored array
let currentWord = [];
//No. of rows = 6
let NUMBER_OF_ROW = 6;
//counting row remaining(no. of row remaining)
let rowRemaining =NUMBER_OF_ROW;
//word filling in particular row
let nextLetter =0;

//How to create Board I already covered in my previous Blog
function createBoard(){
    let cont = document.getElementById("game-board");
    for(let i=0;i<6;i++){
        let row = document.createElement("div");
        row.className="letter-row";
        for(let j=0;j<5;j++){
            let box = document.createElement("div");
            box.className="letter-box";
            row.appendChild(box);
        }
        cont.appendChild(row);
    }
}
createBoard();
//You figure out where the right spot on the board is by checking the number of row the user has left and how many letters the user has entered so far.

//If the key pressed was Enter, you go to the next line.
document.addEventListener("keyup", (e) => {

    let pressedKey = String(e.key)
    //when user pressed a key "Backspace" then run deleteLetter() function
    if (pressedKey === "Backspace" && nextLetter !== 0) {
        deleteLetter()
        return
    }
    //when user pressed a key "Enter" then run nextLine() function
    if(pressedKey==="Enter"){
        nextLine();
        return;
    }
    //Don't allowed pressed key more than 1 letter else pressed key length==1             then run insertLetter() function
    if (pressedKey.split('').length > 1) {
        return
    } else{
        insertLetter(pressedKey)
    }
    if(pressedKey==="Enter"){
        nextLine();
        return;
    }
})

//insertLetter checks that there's still space in the current row for this letter, finds the appropriate row, and puts the letter in the box.
function insertLetter (pressedKey) {
    if (nextLetter === 5) {
        return
    }
    pressedKey = pressedKey.toLowerCase()
    let row = document.getElementsByClassName("letter-row")[6 - rowRemaining]
    let box = row.children[nextLetter]
    box.textContent = pressedKey
    box.classList.add("filled-box")
    currentWord.push(pressedKey)
    nextLetter += 1
}

function deleteLetter () {
    let row = document.getElementsByClassName("letter-row")[6 - rowRemaining]
    let box = row.children[nextLetter - 1]
    box.textContent = ""
    box.classList.remove("filled-box")
    currentGuess.pop()
    nextLetter -= 1
}
function nextLine(){
     rowRemaining -= 1;
     currentWord = [];
     nextLetter = 0;
}
```

**Caution:-** Before you jump into this Blog...Please read my previous Blog([LINK](https://shubhamsigdar.hashnode.dev/how-i-create-the-game-board65-of-wordle-using-javascript))