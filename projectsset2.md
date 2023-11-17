# Projects related to Async Js

## project link
[Click here](https://codesandbox.io/s/random-background-color-changer-forked-9f2xks)

# Solution Code

## project 2

```javascript
// random color generate

const randomColor = function(){
    const hex = "0123456789ABCDEF"
    let color = "#"

    for(let i = 0; i < 6; i++){
      color += Math.floor(Math.random() * 16);
    } 
    return color;
};

let intervalId;
const startChangingColor = function(){
    // we kept a null check so that when the value gets null it will starts new interval
    if(!intervalId){
      intervalId = setInterval(changeBgColor, 1000);
    }
    function changeBgColor(){
      document.body.style.backgroundColor = randomColor();
    }
};

const stopChangingColor = function(){
    // deference the value so that value of intervalId don't get overwrite
    // and gets the fresh value after each stop action
    clearInterval(intervalId);
    intervalId = null;
}
document.querySelector('#start').addEventListener('click', startChangingColor)
document.querySelector('#stop').addEventListener('click', stopChangingColor);
```