# Java Web 
### Polymorphism 
Abstract classes and methods are inherited and implemented in children classes. This logical tree shows a heerarchy of functionality. 

```Java
public Abstract class Shape {
    abstract void draw();
}

public class Circle extends Shape {
    @Override 
    public void draw() {
        // draw the circle
    }
}

public class Square extends Shape {
    @Override 
    public void draw() {
        // draw the square
    }
}
```