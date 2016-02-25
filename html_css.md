# HTML

### Basic Elements 

##### Header stuff 
```html
    <head>
        <link rel="stylesheet" type="text/css" href="./Semantic/semantic.min.css">
        <script src="//code.jquery.com/ui/1.11.4/jquery-ui.js"></script>
        <title>Alec Troemel: A Guy</title>
    </head>
```

##### Images 
```html
<img src="images/4.1.PNG"/>
```

### Forms
```html
<form name="Name" method="get" action="http://was6.itk.ilstu.edu:9080/itk/EchoAll">
    <fieldset>
        ... form stuff here
    </fieldset>
    
    <fieldset>
        ... form stuff here
    </fieldset>
</form>
```

##### Text Input 
```html
<input type="text" name="catalog" />
```

##### Radio Buttons  
```html
<input type="radio" name="foodChoice" value="pizza"> Pizza <br>
<input type="radio" name="foodChoice" value="hotdog"> Hotdog <br>
```

##### Checkboxes 
```html
<input type="checkbox" name="box" value="like"> I like this!<br>
<input type="checkbox" name="box" value="dislike"> ... It could use some 
```

##### Select's 
```html
<select>
    <option>pizza</option>
    <option>hotdog</option>
</select>
```

##### MultiLine Text Input 
```html
<textarea rows="4" cols="50">Type your wonderfull paper here</textarea>
```

##### Button 
```html
<input type="button" value="You cant see me!!" hidden="true">
```

##### Reset Button 
```html
<input type="reset">
```

##### Submit Button 
```html
<input type="submit">
```

### Tables 
```html
<table border="1">
    <tr>
        <th>Number</th>
        <th colspan="2">Things That Are Cool</th>
    </tr>
    <tr>
        <td rowspan="2">1</td>
        <td>C$SH Money</td>
        <td>Internet memes</td>
    </tr>
</table>
```

# CSS
##### classes
```CSS
.class {

}
```

##### ID's
```CSS
#id {

}
```

        

        #id {}

        h {
            background: url(images/boards.jpg) repeat-x;
            background-image: url("./images/background_city.jpg");
            background-repeat: no-repeat;
            background-position: center;
            background-attachment: fixed;
            background-color: white;

            padding: 3%;
            border: 5% 5% 5% 5%;

            width: auto;
            height: auto;

            color: #c1ffd6; /* of font */
            font-weight: bold;
            font-style: italic;
            font-size: 50pt;
            font-family: Arial Rounded MT Bold;
        }  
