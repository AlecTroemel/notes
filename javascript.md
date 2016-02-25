# JavaScript 

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

Work with radio buttons
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