# Java Web 
### Polymorphism 
Abstract classes and methods are inherited and implemented in children classes. Creates a logical tree showing a hierarchy of functionality. This allows for more extendable and generic code.

```Java
public Abstract class Shape {
    abstract void draw();
}

public class Circle extends Shape {
    @Override 
    public void draw() {
        // ... draw the circle
    }
}

public class Square extends Shape {
    @Override 
    public void draw() {
        // ... draw the square
    }
}
```

