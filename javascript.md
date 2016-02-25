# JavaScript 

### Basics
alert
```javascript
    Alert("message");
```

Prompt
```javascript
    var name = prompt("Enter name", "John Deer");
```
    
Confirm 
```javascript
var boolean = confirm("You selected: " + string + ". Is this correct?");   
```
    
For loop 
```javascript
for (var i = 1; i < numberOfScores; i++) {
    ...
}
```

Functions 
```javascript
// basic function, select random color
function randomColor() {
    var allowed = "0369cf".split( '' ), s = "#";
    while ( s.length < 4 ) {
       s += allowed.splice( Math.floor( ( Math.random() * allowed.length ) ), 1 );
    }
    return s;
}

// onSubmit function 
theForm.onsubmit = function() {
    ...
}
```

### Unobtrusive Code 
Separating JavaScript functionality from HTML content  

```html
<a href="http://www.ilstu.edu/">
    <img src="images/button.14.gif" id="image1">    
</a>

<script>
    var v1 = document.getElementById("image1");
    v1.onmouseover = function() {
        v1.src = "images/button.14.on.gif";
    };
    
    v1.onmouseout = function() {
        v1.src = "images/button.14.gif";
    };
</script> 
```

### Working with forms 
get the form object from ID
```javascript
var theForm = document.getElementById("theForm");
```

Working with radio buttons
```javascript
// When the second radio button is checked, the first text field is to be set in focus.
theForm.searchPref[0].onclick=function(){
    theForm.air1.blur();
};   
```

```javascript
// When any of the three text fields is in focus, the second radio button is to be checked.	
for (i = 2; i < theForm.elements.length - 1; i++) {
    theForm.elements[i].onfocus=function(){
        theForm.searchPref[1].checked = true;
    };
}
```

working with text input 
```javascript
// check text input has input 
for (i = 2; i < theForm.elements.length - 1; i++) {
    if (theForm.elements[i].value != "") {
        return true;
    }
}
```

### Dynamic creation of html elements 
```javascript
for (i = 0; i < names.length; i++) {
    var temp = document.createElement("div");

    var color = randomColor();
    temp.style = "background-color:" + color;
    temp.className = "name";

    var header = document.createElement("h1");
    var node = document.createTextNode(names[i]);
    header.appendChild(node);         
    temp.appendChild(header);


    var element = document.getElementById("container");
    element.appendChild(temp);
    divsList.push(temp);
    onTopIndex = i;
    divsList[i].style.animation = "hide 1s forwards";
    divsList[i].style.animationPlayState = "play";
}
```

### on Click to select the name 
```javascript
var button = document.getElementById("button");
function selectName() {
    // pick a number that is not on top
    var indexNum = Math.floor((Math.random() * names.length));  
    while (indexNum == onTopIndex) {
        indexNum = Math.floor((Math.random() * names.length)); 
    }

    //alert(indexNum);
    var newTopIndex;
    for (i = 0; i < names.length; i++) {
        if(indexNum == i) {
            divsList[i].style.animation = "show 1s forwards";
            divsList[i].style.animationPlayState = "play";
            newTopIndex = i;
        }
        else if (i == onTopIndex) {
            divsList[i].style.animation = "hide 1s forwards";
            divsList[i].style.animationPlayState = "play";
        }
    }
    onTopIndex = newTopIndex;
}; 
```

### Some Example Code
```javascript
function myFunc() {
    var firstname = prompt("Please enter your first name", "Pizza");

    if (firstname == "" || firstname == null ) {
        alert("you didn't say anything...");  
    }
    else {
        var lastname = prompt("Now your last name", "Hotdog");    

        if (lastname == "" || lastname == null) {
            alert("you didn't say anything...");  
        }
        else {
            alert("Hello " +lastname + ", " + firstname + "! Welcome to ITK353.");
        }            
    }
}
```

```javascript 

```

```javascript 
function validateEmail(emailString) { 
    
    // check if there are multiple at signs 
    if ((emailString.split("@").length - 1) > 1) {
        alert(emailString + "Incorrect: Email may not have more than 1 @ sign ");
        return false;
    }
    
    // check at positions
    var atPosition = emailString.indexOf("@");
    if (atPosition == -1) {
        alert(emailString + "Incorrect: Email must have @ sign ");
        return false;
    }
    else if (atPosition == 0) {
        alert(emailString + "Incorrect: @ sign may not be a beginning ");    
        return false;
    }
    else if (atPosition == emailString.length - 1) {
        alert(emailString + "Incorrect: @ sign may not be a end ");    
        return false;
    }
    
    // check dot position after at sign
    var afterAt = emailString.substr(atPosition + 1);
    var dotPosition = afterAt.indexOf(".");
    if (dotPosition == -1) {
        alert(emailString + "Incorrect: Email must have domain name with . ");
        return false;
    }
    else if (dotPosition == 0) {
        alert(emailString + "Incorrect: . sign may not be directly after @ sign ");    
        return false;
    }
    else if (dotPosition == afterAt.length - 1) {
        alert(emailString + "Incorrect: . sign may not be a end ");    
        return false;
    }
    
    return true;
}
```



