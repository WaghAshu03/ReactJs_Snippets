# Grid Pattern in React

## Sample Image:
<center><img src="./BoxGrid_img1.jpg" width="600"/></center>
<br>

## How To Include:
### Step 1: Create BoxGrid.js and BoxGrid.css and copy below code.

### BoxGrid.js

```javascript
import React from "react";
import './BoxGrid.css';

const GridBox = (props) => { 
  let temp = "";
  for(let i = 0; i < props.BoxesInARow; i++){
    temp = temp + "auto ";
  }
  console.log(temp);

  document.getElementById("GridContainer").style.gridTemplateColumns = temp;
  
  const list = []
  for (let i = 0; i < props.NoOfBoxes; i++) {
    list.push(
      <div class="GridContainerBox" 
      style={{
        width: props.BoxWidth,
        height: props.BoxHeight,
        outline: props.BoxOutline,
        background: props.BoxBackground
      }} />
    )
  }

  return (
    <>
    <div className="GridContainer" id="GridContainer">
      {list}
    </div>
    </>
  )
};

export default GridBox;
```

### BoxGrid.css
```css
.GridContainer{
    display: grid;
    grid-gap: 0px;
    width: fit-content;   
}
```

### Step 2: Import BoxGrid

```javascript
import "./App.css";
import BoxGrid from "./BoxGrid";

function App() {
  return (
    <div className="App">
      <BoxGrid
        BoxesInARow="10" // Total No. Of Boxes in a Row
        NoOfBoxes="100"  // Total Boxes Your Grid
        BoxWidth="40px"  // Width of a Box
        BoxHeight="40px"  // Height of a Box
        BoxOutline="1px solid black" // Outline of a Box
        BoxBackground= "skyblue" // Background Style of a Box
      />
    </div>
  );
}

export default App;
```

## Examples:
### Example 1:
```html
<BoxGrid
    BoxesInARow="5"
    NoOfBoxes="23"
    BoxWidth="40px" 
    BoxHeight="40px" 
    BoxOutline="2px solid Black"
/>
```
<img src="./BoxGrid_img2.jpg" width="600"/>

<br>

### Example 2:
```html
<BoxGrid
    BoxesInARow="8"
    NoOfBoxes="64"
    BoxWidth="40px" 
    BoxHeight="40px" 
    BoxOutline="2px solid red"
    BoxBackground= "yellow"
/>
```
<img src="./BoxGrid_img3.jpg" width="600"/>


## [Go Back To Main Page](../README.md)