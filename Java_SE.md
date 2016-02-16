###Namespace
allows you to enter a specific context of a code package or module to remove ambiguity/ having multiple namespace's with the same methods.

this is how it is done in xhtml
```xml
    xmlns:h="http://java.sun.com/jsf/html"
    <h:form></h:form>
```
### EL (Expression langauge)
used to reference object properties in the back end 

```xml
#{profileController.theModel.clientName}
```

### MVC
MVC stands for Model View Controller and is a design pattern that separates the functionality and user interface into clear interconnected parts. 
* Model: the behavior and actions of the application 
* View: the user interface side, what the user interacts with 
* controller: accepts input and turns it into commands for the model or view

This is a great way to develop because different teams can focus on a specific aspect of the pattern without worrying about the others. 
### Managed Bean 
A bean is basically a class with some well defined properties. A managed bean is a bean handles by the java SS framework. 