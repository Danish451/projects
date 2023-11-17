# Projects related to Async Js

## project 1
## project link
[Click here](https://codesandbox.io/s/keyboard-key-forked-68csry)
# Solution Code
```javascript
const insert = document.getElementById('insert');

window.addEventListener('keydown', (e) => {
  insert.innerHTML = `
    <div class='color'>
    <table>
    <tr>
      <th>Key</th>
      <th>Keycode</th> 
      <th>Code</th>
    </tr>
    <tr>
      <td>${e.key === ' ' ? 'Space' : e.key}</td>
      <td>${e.keyCode}</td> 
      <td>${e.code}</td>
    </tr>
    
  </table>
    </div>
  `;
});

```
## project 2
## project link
[Click here](https://codesandbox.io/s/random-background-color-changer-forked-9f2xks)

# Solution Code
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