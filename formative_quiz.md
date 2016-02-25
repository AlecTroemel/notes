# Formative-quiz: Solution

###Multiple Choice:

**1.** If the three classes in the following inheritance hierarchy contain a calculateMaxSpeed method, which class defines the method that is called when the 2nd statement in the code that follows is executed?

* Object
    * Vehicle
        * MotorVehicle
            * Automobile

```java 
MotorVehicle car = new Automobile();
car. calculateMaxSpeed();
```
__d) Automobile__

**2.** T/F: Abstract class can only contain abstract methods, not non-abstract ones (i.e. methods with bodies).

**False. Unlike interfaces, abstract class can contain non-abstract methods.**

###HTML/CSS:

**3. **Write a CSS doc to style each "important" class to yellow and each anchor to bold and italics. Now, write an HTML doc to test the CSS doc. 
```html
<style>
    .important {
     background-color: yellow;
    }
    
    a {
     font-weight: bold;
     font-style: italic;
    }
    
    a:link  {color:blue; text-decoration:none;}
    a:visited {color:#000000}
    a:hover   {color:#ff0000}
    a:active  {color:#ff0000}
</style>

<!DOCTYPE html>
<html>
    <head>
        <link rel="stylesheet" type="text/css" href="./css/quiz.css">
    </head>
    
    <body>
        <h1>I am formatted with a linked style sheet</h1>
        <h1>I am formatted with a linked style sheet also</h1>
        <p>Me too!</p>
        <p>Me three!</p>
        <h1 class="important">But I have class!</h1>
        <a href="http://cnn.com">CNN News</a>
    </body>

</html>
```
JavaScript:

[10 pts] 4. Write a JavaScript validation function to make sure that the even characters of a serial number are digits. Submit if validated successfully and abort otherwise.

<!DOCTYPE html>
<html>
<head><title>Quiz Q</title><h3>... even characters of a serial number are digits ... </h3>
<SCRIPT>
function validate(aForm) {
   var isBad = false;
   var serial = aForm.number.value;
   for (var i = 1; i <= serial.length; i++) { // note starting at 1
      if (i % 2 == 0) // even
          if (!isDigit(serial.charAt(i-1))) {
              isBad = true; 
              break;
          }
   }
   if (isBad) { 
       alert("the serial # is bad");
       return false;
   }
   else {
       alert("the serial # is good");
       return true;
   }
}
//-------------------------------------------------------------------
// Source: http://www.mattkruse.com/javascript/validations/source.html
// isDigit(value)
//   Returns true if value is a 1-character digit
//-------------------------------------------------------------------
function isDigit(num) {
    if (num.length>1){
     return false;
    }
 var string="1234567890";
    if (string.indexOf(num)!=-1){
     return true;
    }
    return false;
}
</SCRIPT>
</head>
<body>
<form onsubmit="return validate(this)" method="get" action="http://was6.itk.ilstu.edu:9080/itk/EchoAll"><BR>
Enter serial #: <INPUT TYPE="text" NAME="number" SIZE="20"> <input type="submit"> 
</form>
</body>

</html>


[8 pts] 5. Consider the following code segment:
<form>
<input type="text" name="myText">
<input type="button" name="myButton" value="Click Me" 
 onClick="__________" >
</form>

Explain the differences among the following function calls with the onClick event handler. Specifically, what is passed to the function and how does one access the value of the text field (in the doThis function) in each of the calls below? For functions that take a parameter, assume the name of the parameter is param1.
(a)     onClick="doThis(this)"

[2 pts] What is passed to the function? ______the button______________________

[2 pts] How to access to the value of the textfield?__document.forms[0].myText.value_or     
                                                                    __ param1.form.myText.value_

(b)     onClick="doThis(this.form)"

[2 pts] What is passed to the function? _______the form_____________________

[2 pts] How to access to the value of the textfield?____param1.myText.value____________________________


Java:

[6 pts] 6. Given the following Address class, complete the method below to tell if a given address contains "College Ave" in its street name?

public class Address {
  
   private String street;
   private String city;
   private String state;
   private String zip;
 
      public Address () {
      }

      public Address (String street, String city, String state, String zip) {
      this.street = street;
      this.city = city;
      this.state = state;
      this.zip = zip;
   }
 
   // gets and sets methods for each of the fields here
}
        
        // In some class:
    public void printAddressWithCollegeAve(Address addrs[]) {
        // TO-DO
        for (int i = 0; i < addrs.length; i++)
         if (addrs[i].getStreet().indexOf("College Avenue") != -1)
             System.out.println(addrs[i]);
    }

JUnit:

[6 pts] 7. The absolute value |a| of a number a is the numerical value of a without regard to its sign (see formula below). So, for example, the absolute value of 3 is 3, and the absolute value of -3 is also 3 (Wikipedia).
 
|a| = \begin{cases} a, & \mbox{if }  a \ge 0  \\ -a,  & \mbox{if } a < 0. \end{cases} 

The Math class in Java has a static method abs(int i) that implements the above. Write a JUnit test class (just the test methods will do) to test if the abs(int i) method correctly implements the specs.

@Test
public void TestGTZero() {
    assertEquals(Math.abs(3),3);  
}
@Test
public void TestEQZero() {
    assertEquals(Math.abs(0),0);  
}
@Test
public void TestLTZero() {
    assertEquals(Math.abs(-3),3);  
}

8. [6 pts] In this question, you are to partially develop a WebApp that performs arithmetic computation (i.e., does +, -, *, and / operations). Assume that a CalculatorBean has already been developed and it supports the above 4 operations. Also, the controller class is given with all the necessary pieces as well. Your job is to write the view (index.xhtml) of the WebApp, which should resemble the screenshot given below. 

Note: Much like how properties from a model/controller can be mapped to elements found in a view (e.g., number 1 is mapped to arg1), a method in a model/controller can also be mapped to an action found in a view. Thus, when an operation such as Add is clicked, a corresponding method can be called to handle the event.

To help with this, check out the project CalcWebApp on the T: drive (which contains the aforementioned pieces).


Download the index.xhtml file and place it on the CalcWebApp webapp (under Web Pages node).