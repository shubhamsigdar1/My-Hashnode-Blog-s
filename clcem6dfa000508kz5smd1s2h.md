---
title: "How I Build Lift Simulation Using HTML, CSS, and JavaScript"
seoTitle: "How I Build Lift Simulation Using HTML, CSS, and JavaScript."
seoDescription: "This is a task given by @realdevsquad and I am also suggesting you all do this task. GitHub Link of this task)"
datePublished: Mon Jan 02 2023 09:43:29 GMT+0000 (Coordinated Universal Time)
cuid: clcem6dfa000508kz5smd1s2h
slug: how-i-build-lift-simulation-using-html-css-and-javascript
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1672650720118/bb606a42-4be4-402a-8e91-552957f49fbe.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1672652533414/96fad207-d491-44af-b6e8-68cec8861d5c.png
tags: css, javascript, html5, 100devs, wemakedevs

---

**Hi everyone,**

**Welcome to my blog. In this post, I will show you how to code your first DOM project.**

In this project, I Have to Create a web app where you can simulate lift mechanics for a client. (This is a task given by [@realdevsquad](https://twitter.com/RealDevSquad) and I am also suggesting you all do this task. [GitHub Link of this task](https://github.com/Real-Dev-Squad/Lift-Simulation))

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672651418144/2bc4e7f4-6e11-4a1b-bdad-321a948fc3df.gif align="center")

Link- [https://lift-simulation-realdev.netlify.app/](https://lift-simulation-realdev.netlify.app/)

GitHub- [https://github.com/shubhamsigdar1/Lift-simulation](https://github.com/shubhamsigdar1/Lift-simulation)

### What is DOM?

---

When we do rendering/Painting on our HTML and CSS in a browser i.e. make some changes and as we refresh our webpage all those changes are gone i.e. we re-rendered or repainted our HTML and CSS files i.e. called DOM

### How we can add behavior and interaction to DOM so that we can manipulate the DOM?

---

**We use JavaScript to manipulate the DOM**

> **Note:-When we manipulate the DOM, We do not manipulate with actual HTML, CSS file**

## How to get started?

---

**1\. Install VS Code \*\* https://code.visualstudio.com/download**

**2\. Install the extension(open in browser) in Vs Code.**

**3\. In your text editor, create a folder Daily Music Generator and then create three separate files i.e. HTML, CSS, and JavaScript. This basically makes your code more organized.**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657752296168/KPwXgKXuW.png align="left")

## Let's Start working on projects

---

**First, we start from HTML files, where you can link CSS and JavaScript files using the code below:**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656046565744/r2DHZ-f9B.png align="left")

# Requirements of Project

---

1. Have a page where you input the number of floors and lifts from the user
    
2. An interactive UI is generated, where we have visual depictons of lifts and buttons on floors
    
3. Upon clicking a particular button on the floor, a lift goes to that floor
    

**Milestone 1:**

* Data store that contains the state of your application data
    
* JS Engine that is the controller for which lift goes where
    
* Dumb UI that responds to controller's commands
    

**Milestone 2:**

* Lift having doors open in 2.5s, then closing in another 2.5s
    
* Lift moving at 2s per floor
    
* Lift stopping at every floor where it was called
    
* Mobile friendly design
    

## Below is the HTML code

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
    <link rel="stylesheet" href="main.css" />
    <title>Linked List</title>
  </head>

  <body>
    <div class="firstPage">
      <h1 class="page-heading">Lift Simulation</h1>
      <div class="noOfFloor input_container">
        <label for="floorNumber">Number of floors</label>
        <input type="Number" id="floorNumber" class="lift-sim_input" placeholder="Enter Upto 7 floors" required/>
      </div>
      <div class="noOfLift input_container">
        <label for="liftNumber">Number of lifts</label>
        <input type="Number" id="liftNumber" class="lift-sim_input"  placeholder="Enter Atleast 2 lifts" required/>
      </div>
      <button class="createLiftFloorButton">Simulate</button>
      <div class="social">
        <a href="https://github.com/shubhamsigdar1" target="_blank"><i class="fa fa-github" style="font-size:30px;color:black"></i></a>
        <a href="https://www.linkedin.com/in/shubhamsigdar" target="_blank"><i class="fa fa-linkedin" style="font-size:30px;color:black"></i>
        </a>
    </div>
    </div>
    <div class="secondPage">
      <button class="goToFirstPage">Back</button>
    </div>
    <script src="main.js"></script>
  </body>
</html>
```

### Below is the CSS code

```css
*{
    margin: 0;
    padding: 0;
}
:root {
    --font-primary: "Bebas Neue", cursive;
    --font-secondary: "Inter", sans-serif;
    --color-dark-800: #212529;
    --color-gray-400: #dddddd;
    --base-transition: 0.4s ease;
    --radius-10: 10px;
    --color-purple-600: #7c27ce;
    --color-light-100: #fff;
  }

  /* <div class="firstPage"> */
.firstPage{
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  height: 100vh;
  transition: var(--base-transition);
}
/* <h1 class="page-heading">Lift Simulation</h1> */
.page-heading {
    font-family: var(--font-secondary);
    font-size: 4rem;
    letter-spacing: 2px;
    text-align: center;
    margin-bottom: 1rem;
    color: var(--color-dark-800);
}
/* <div class="noOfFloor input_container">
        <label for="floorNumber">Number of floors</label>
        <input type="Number" id="floorNumber" class="lift-sim_input" placeholder="Enter Upto 7 floors" required/>
    </div> */
.input_container{
    display: flex;
    flex-direction: column;
    margin-bottom: 1rem;
}

label,
input {
  font-family: var(--font-secondary);
}

label{
    margin-left: 20%;
}

/* <input type="Number" id="liftNumber" class="lift-sim_input"  placeholder="Enter Atleast 2 lifts" required/> */
.lift-sim_input {
    padding: 5px 10px;
    font-size: 1rem;
    border-radius: var(--radius-10);
    margin-top: 5px;
    min-width: 250px;
    border: 2px solid var(--color-gray-400);
    transition: var(--base-transition);
  }

.lift-sim_input:focus {
    border-color: var(--color-dark-800);
}
/* <button class="createLiftFloorButton">Simulate</button> */
.createLiftFloorButton{
    margin-top: 1rem;
  padding: 5px 10px;
  font-size: 1.5rem;
  font-family: var(--font-secondary);
  border: 2px solid var(--color-gray-400);
  border-radius: var(--radius-10);
  cursor: pointer;
  transition: var(--base-transition);
}
/* <div class="social">
        <a href="https://github.com/shubhamsigdar1" target="_blank"><i class="fa fa-github" style="font-size:30px;color:black"></i></a>
        <a href="https://www.linkedin.com/in/shubhamsigdar" target="_blank"><i class="fa fa-linkedin" style="font-size:30px;color:black"></i>
        </a>
    </div> */
.social {
    margin-top: 15px;
}
.social a{
    margin: 0px 10px;
    color: blue;
}
  

/* dynamically create buttons, lift,gates */
/* <div class="box">
      <div class="buttonLift">
          <div class="button">
              <button class="up" id="up1">Up</button>
              <button class="down" id="down1">Down</button>
           </div>
           <div class="mainLift">
              <div class="lift" id="lift1" flag="free">
                <div class="gates" id="gates">
                   <div class="gate1"></div>
                   <div class="gate2"></div>
                </div>
               <div>
            </div>
        </div>
        <div class="hrfloorName">
            <hr>
            <span>Floor 1</span>
        </div>
    </div> */
.buttonLift{
    display: flex;
}

.button{
    width:50px;
    display: flex;
    flex-direction: column;
    margin: 11px 18px;
 }

 .button button{
    margin: 2px;
 }
.up{
    font-size: 13px;
    border-radius: 4px;
    transition-duration: 0.4s;
    background-color: white;
    color: var(--color-dark-800);
}
.down{
    font-size: 13px;
    border-radius: 4px;
    transition-duration: 0.4s;
    background-color: white;
    color: var(--color-dark-800);
}
.up:hover{
    background-color: black;
    color: white;
}
.down:hover{
    background-color: black;
    color: white;
}

.mainLift{
    display: flex;
    margin-left: 10px;
}
.lift{
    width: 50px;
    height: 60px;
    background-color: var(--color-gray-400);
    border: 2px solid black;
    margin-right: 5px;
    transition-property:transform;
    transition-timing-function:ease-in;
}

.gates{
    display: flex;

}
.gate1 , .gate2{
    width: 25px;
    height: 60px;
    margin: 1px;
    background-color:var(--color-dark-800);
    transition: width 2.5s ease-in-out;
}
.gate1-move{
    transform: translateX(-100%);
}

.gate2-move{
    transform: translateX(100%);
}

/* second page ko none krh de rha hai */
.secondPage{
    display: none;
    margin: 4% auto;
}
.hrfloorName{
    display: flex;
    flex-direction: row;
    margin: 3px;
}
hr{
    flex-grow:1;
    height: 1px;
    border-top: 2px solid black;
} 

h2 {
    width: 100%; 
    text-align: center; 
    border-bottom: 1px solid #000; 
    line-height: 0.1em;
    margin: 10px 0 20px; 
 } 
 
 h2 span { 
     background:#fff; 
     padding:0 10px; 
 }

.goToFirstPage{
    font-size: 18x;
    margin: 5px 0 10px 3px ;
    background-color:var(--color-dark-800);
    color: white;
    width: 80px;
    height: 30px;
    cursor: pointer;
}

 @media (width>500px){
    .lift{
        margin-right: 55px;
    }
    .mainLift{
        margin-left: 50px;
    }
}
```

### Below is the JavaScript code

**Please see the comment if you aren't able to understand**

```javascript


let simulate = document.querySelector('.createLiftFloorButton');
// console.log(simulate);<button class="createLiftFloorButton">Simulate</button>

let restart = document.querySelector('.goToFirstPage');
//console.log(restart) <button class="goToFirstPage">Back</button>

//adding eventListener click on button back
restart.addEventListener('click', hideSecondPage);

//add event listener on button simulate and e means event
simulate.addEventListener('click', ()=> {

    //when we click simulate button please collect the input no. of floor and lift value
    let floorInputValue=document.querySelector('#floorNumber').value;
    let liftInputValue=document.querySelector('#liftNumber').value;
    // console.log(floorInputValue);
    // console.log(window.innerWidth);

    //if we don't give input no. of floor and lift value
    if(floorInputValue=="" || liftInputValue==""){
        alert('please enter the value')
    }
    //if we give input no. of floor>=8 
    else if(floorInputValue>=8){
        alert('please enter max 7 floor')

    }
    //if media query width of window<=500 and (+)means convert string into number
    //i do this to make lift simulation everydevice size friendly 
    else if (window.innerWidth <= 500 && +liftInputValue > 4) {
        alert("This screen size can't have more than 4 lifts");
    }
    else if (window.innerWidth > 500 && window.innerWidth <= 768 && +liftInputValue > 5) {
        alert("This screen size can't have more than 5 lifts");
    }
    else if (window.innerWidth > 500 && window.innerWidth <= 1024 && +liftInputValue > 7) {
        alert("This screen size can't have more than 7 lifts");
    }
    else if (window.innerWidth > 500 && window.innerWidth <= 1440 && +liftInputValue > 11) {
        alert("This screen size can't have more than 11 lifts");
    }
    else if (window.innerWidth > 500 && window.innerWidth <= 2560 && +liftInputValue> 20) {
        alert("This screen size can't have more than 20 lifts");
    }

    //when simulate button clicked hide .firstPage class div and display .secondPage class div
    else{
        document.querySelector('.firstPage').style.display = 'none';
        document.querySelector('.secondPage').style.display = 'block';
        // console.log('second')
        makingFloors();
    }
});

//when  button back clicked hide .secondPage class div and display .firstPage class div
function hideSecondPage() {
    document.querySelector('.secondPage').style.display = 'none';
    document.querySelector('.firstPage').style.display = 'flex';
    
    deletingFloors();

}

//Now Lets create a floor 

/* <div class="box">
<div class="buttonLift">
    <div class="button">
        <button class="up" id="up1">Up</button>
        <button class="down" id="down1">Down</button>
     </div>
     <div class="mainLift">
        <div class="lift" id="lift1" flag="free">
          <div class="gates" id="gates">
             <div class="gate1"></div>
             <div class="gate2"></div>
          </div>
         <div>
      </div>
  </div>
  <div class="hrfloorName">
      <hr>
      <span>Floor 1</span>
  </div>
</div> */
function makingFloors() {
    
    // collect the input no. of floor and lift value
    let floorInput = document.querySelector('#floorNumber').value;
    let liftInput = document.querySelector('#liftNumber').value;
   

    for (let i = floorInput; i > 0; i--) {
        // <div class="box"></div>
        let floordiv = document.createElement('div');
        floordiv.className = 'box';

        // <div class="buttonLift"></div>
        let buttonLift = document.createElement('div');
        buttonLift.className = 'buttonLift';
        
        // <div class="button"></div>
        let buttondiv1 = document.createElement('div');
        buttondiv1.className = 'button';

        //button1 create
        // <button class="up" id="up1">Up</button>
        let button1 = document.createElement("button");
        let text1 = document.createTextNode("Up");
        button1.className = "up";
        button1.setAttribute('id', `up${i}`);
        button1.appendChild(text1);

        // select krh rha hu button id

        //button2 create 
        // <button class="down" id="down1">Down</button>
        let button2 = document.createElement("button");
        let text2 = document.createTextNode("Down");
        button2.className = "down";
        button2.setAttribute('id', `down${i}`);
        button2.appendChild(text2);

        //button1 and button2 append in this div <div class="button"></div>
        buttondiv1.appendChild(button1);
        buttondiv1.appendChild(button2);

        // buttondiv1 append in <div class="buttonLift"></div>
        buttonLift.appendChild(buttondiv1);

        //buttonLift append in this div <div class="box"></div>
        floordiv.appendChild(buttonLift);


        //Creating HrFloor
        //<div class="hrfloorName"></div>
        let hrdiv = document.createElement('div');
        hrdiv.className = 'hrfloorName';
        
        //<hr>
        let hr = document.createElement('hr');

        //<span>Floor 1</span>
        let spanFloorNo = document.createElement('span');
        spanFloorNo.innerText = `Floor ${i}`;
        
        //<hr> append in this div <div class="hrfloorName"></div>
        hrdiv.appendChild(hr);

        //<span>Floor 1</span> append in this div <div class="hrfloorName"></div>
        hrdiv.appendChild(spanFloorNo);
  
        //<div class="hrfloorName"></div> is append in this div <div class="box"></div>
        floordiv.appendChild(hrdiv);
         
        //<div class="box"></div>  is append in this div <div class="secondPage"></div>
        document.querySelector('.secondPage').appendChild(floordiv);
    }
      

//lets create a lift i.e. 

// this is whole we create in below
//   <div class="mainLift">
//     <div class="lift" id="lift1" flag="free">
//       <div class="gates" id="gates">
//          <div class="gate1"></div>
//          <div class="gate2"></div>
//       </div>
//      <div>
//   </div>

    // <div class="mainLift"></div>
    let mainLift = document.createElement('div');
    mainLift.className = 'mainLift';

    for (let j = 1; j <= liftInput; j++) {

        // <div class="lift" id="lift1" flag="free"></div>
        let liftdiv = document.createElement('div');
        liftdiv.className = 'lift';
        liftdiv.setAttribute('id', `lift${j}`);

        //adding flag="free" attribute in <div class="lift" id="lift1" flag="free"></div>
        liftdiv.setAttribute('flag', `free`);

        // <div class="gates" id="gates"></div>
        let gates = document.createElement('div');
        gates.className = 'gates';
        gates.setAttribute('id', `gates`);

        // <div class="gate1"></div>
        let gate1 = document.createElement('div');
        gate1.className = 'gate1';
        // <div class="gate1"></div> append in this div <div class="gates" id="gates"></div>
        gates.appendChild(gate1);

        // <div class="gate2"></div>
        let gate2 = document.createElement('div');
        gate2.className = 'gate2';
        // <div class="gate2"></div> append in this div <div class="gates" id="gates"></div>
        gates.appendChild(gate2);

        // <div class="gates" id="gates"></div> append in this div <div class="lift" id="lift1" flag="free"></div>
        liftdiv.appendChild(gates);

        // <div class="lift" id="lift1" flag="free"></div> append in this div <div class="mainLift"></div>
        mainLift.appendChild(liftdiv);
    }

    // Now, We want to add all lifts we created above in last box button div i.e.

    //   <div class="box">
    //     <div class="buttonLift">
    //        <div class="button">
    //           <button class="up" id="up1">Up</button>
    //           <button class="down" id="down1">Down</button>
    //         </div>
    //     </div> 

    //selecting all the div class .buttonLift we created using querySelectorAll 
    const mainbuttonlift = document.querySelectorAll('.buttonLift');
    // console.log(mainbuttonlift); 

    //selecting last div class .buttonLift 
    const lastbox = mainbuttonlift[mainbuttonlift.length - 1];
    // console.log(lastbox)

    // <div class="mainLift"></div> append in this div <div class="buttonLift"></div>
    lastbox.appendChild(mainLift);



    //  select all lift we created above using querySelectorAll
    let selectAllLift = document.querySelectorAll('.lift');
    // console.log('s',selectAllLift)

    // select all up button <button class="up" id="up1">Up</button> using querySelectorAll
    let up = document.querySelectorAll('.up');

    // select all down button <button class="down" id="down1">Down</button> using querySelectorAll
    let down = document.querySelectorAll('.down');

    //store no. of lifts in nUp
    let nUp = up.length;
    let prev = 0;
    
    //create oldFloorValueArray for calculation purpose
    let oldFloorValueArray=[];

    for(let i=0;i<selectAllLift.length;i++){
        oldFloorValueArray.push(1)
    }
    // console.log(oldFloorValueArray)//oldFloorValueArray=[1,1,1,1];

    //Now we loop through all up button and add eventListener in all up button
    up.forEach((e, i) => {
        e.addEventListener('click', () => {

            //create floorValue for calculation purpose
            let floorValue = nUp - i;
            for (let i = 0; i < selectAllLift.length; i++) {
                // console.log(selectAllLift)

                //check <div class="lift" id="lift1" flag="free"> lift attribute flag has value free
                if (selectAllLift[i].getAttribute('flag') === 'free') {
                    // set attribute flag value busy i.e. <div class="lift" id="lift1" flag="busy">
                    selectAllLift[i].setAttribute('flag', 'busy');

                    //call a function moveLift
                    moveLift(selectAllLift[i], floorValue,oldFloorValueArray[i]);
                    oldFloorValueArray[i]=floorValue;
                    // console.log(oldFloorValueArray);
                    // console.log(selectAllLift[i]);
                    break;
                }
            }
        })
    })


    //same steps like above we do in up button now we are going to do in down buttons 
    down.forEach((e, i) => {
        e.addEventListener('click', () => {
            let floorValue = nUp - i;
            for (let i = 0; i < selectAllLift.length; i++) {
                // console.log(selectAllLift)
                if (selectAllLift[i].getAttribute('flag') === 'free') {
                    selectAllLift[i].setAttribute('flag', 'busy');
                    moveLift(selectAllLift[i], floorValue,oldFloorValueArray[i]);
                    oldFloorValueArray[i]=floorValue;
                    // console.log(oldFloorValueArray);
                    // console.log(selectAllLift[i]);
                    break;
                }
            }
        })
    })
}


function moveLift(liftno, floorNo,oldFloorValue) {
    
    //add styling transform to move lift smooth in Y direction using transform property
    liftno.style.transform = `translateY(${-95 * (floorNo - 1)}px)`;

    // add styling transition-duration to particular lift i.e. we do this because Lift moving at 2s per floor 
    let prev= `${2 * Math.abs(floorNo - oldFloorValue)}s`
    liftno.style.transitionDuration = prev;
    // console.log('snjh',2*(floorNo -oldFloorValue));
    

    
    //What we are doing in below steps
    // we want that Lift stopping at every floor where it was called after 2sec we set attribute flag value free
    // and then we want ki Lift having doors open in 2.5s, then closing in another 2.5s for that we call function gateopenclose(liftno);
    setTimeout(() => {
        
        gateopenclose(liftno);
        setTimeout(() =>{
            liftno.setAttribute('flag', 'free')
        },5500);
        console.log(liftno.getAttribute('flag'))
    }, 2 * Math.abs(floorNo - oldFloorValue) * 1000)
 
} 

function gateopenclose(liftno) {
    let gates=liftno.firstChild; 
    let gate1 = document.querySelector('.gate1');
    let gate2 = document.querySelector('.gate2');

    //gate open in 1sec and you see gate open smoothly because i decrease the width and 
    // add transition property in css in class .gate1 , .gate2
    setTimeout(() => {
//     <div class="gates" id="gates">
//         <div class="gate1"></div> gates.children[0]
//         <div class="gate2"></div>gates.children[1]
//     </div>
        gates.children[0].style.width = '3px';
        gates.children[1].style.width = '3px';
    }, 1000);

    // gate close in 3.5s
    setTimeout(() => {
        gates.children[0].style.width = '25px';
        gates.children[1].style.width = '25px';
    }, 3500)
}


//after clicking back button we want that all floor <div class="box"></div> we created dynamically 
// should be deleted using remove built-in method
function deletingFloors() {
    let floorInput = document.querySelector('#floorNumber').value;

    for (let i = floorInput; i > 0; i--) {
        let floordiv = document.querySelector('.box');
        floordiv.remove();
    }
}
```

**If you liked this article, consider following me on** **Hashnode** **for my latest publications.**