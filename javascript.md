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