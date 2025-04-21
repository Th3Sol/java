### 1. Write a program for implementation of different methods of  
**a. string class**  
**b. stringbuffer class**
```java
public class StringDemo {
    public static void main(String[] args) {
        // String class methods
        String str = "Hello World";
        System.out.println("Length: " + str.length());
        System.out.println("Upper: " + str.toUpperCase());
        System.out.println("Substring: " + str.substring(0, 5));
        System.out.println("CharAt: " + str.charAt(1));

        // StringBuffer class methods
        StringBuffer sb = new StringBuffer("Hello");
        sb.append(" World");
        System.out.println("Appended: " + sb);
        sb.insert(5, " Java");
        System.out.println("Inserted: " + sb);
        sb.replace(6, 10, "Awesome");
        System.out.println("Replaced: " + sb);
        sb.reverse();
        System.out.println("Reversed: " + sb);
    }
}
```



### 2. Write a program to implement a multidimensional array.
```java
public class MultiArray {
    public static void main(String[] args) {
        int[][] arr = {
            {1, 2, 3},
            {4, 5, 6}
        };
        for (int i = 0; i < arr.length; i++) {
            for (int j = 0; j < arr[i].length; j++) {
                System.out.print(arr[i][j] + " ");
            }
            System.out.println();
        }
    }
}
```



### 3. Write a program to implement a parameterized constructor.
```java
class Student {
    String name;
    int age;

    Student(String n, int a) {
        name = n;
        age = a;
    }

    void display() {
        System.out.println("Name: " + name + ", Age: " + age);
    }

    public static void main(String[] args) {
        Student s1 = new Student("Th3", 17);
        s1.display();
    }
}
```



### 4. Write a program to implement multilevel inheritance.
```java
class Animal {
    void sound() {
        System.out.println("Animal makes sound");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Dog barks");
    }
}

class Puppy extends Dog {
    void weep() {
        System.out.println("Puppy weeps");
    }

    public static void main(String[] args) {
        Puppy p = new Puppy();
        p.sound();
        p.bark();
        p.weep();
    }
}
```



### 5. Develop a program to find the area of rectangle & circle using interfaces.
```java
interface Shape {
    void area();
}

class Rectangle implements Shape {
    int length = 5, breadth = 3;

    public void area() {
        System.out.println("Area of Rectangle: " + (length * breadth));
    }
}

class Circle implements Shape {
    double radius = 4;

    public void area() {
        System.out.println("Area of Circle: " + (3.14 * radius * radius));
    }

    public static void main(String[] args) {
        Rectangle r = new Rectangle();
        Circle c = new Circle();
        r.area();
        c.area();
    }
}
```



### 6. Write a program to implement user defined packages in terms of creating a new package and importing the same.

**Step 1: Create a file named `mypack/MyClass.java`:**
```java
package mypack;

public class MyClass {
    public void display() {
        System.out.println("Hello from user-defined package!");
    }
}
```

**Step 2: Create a separate file in the same level:**
```java
import mypack.MyClass;

public class TestPackage {
    public static void main(String[] args) {
        MyClass obj = new MyClass();
        obj.display();
    }
}
```

**Compile commands:**
```
javac mypack/MyClass.java  
javac -cp . TestPackage.java  
java -cp . TestPackage
```



### 7. Write a program for implementation of try, catch and finally block.
```java
public class TryCatchFinally {
    public static void main(String[] args) {
        try {
            int a = 10 / 0;
        } catch (ArithmeticException e) {
            System.out.println("Error: Cannot divide by zero");
        } finally {
            System.out.println("Finally block executed");
        }
    }
}
```



### 8. Write a program to display the number on button from 0 to 9
```java
import java.awt.*;
import java.awt.event.*;

public class NumberButtons extends Frame {
    NumberButtons() {
        setLayout(new GridLayout(2, 5));
        for (int i = 0; i <= 9; i++) {
            Button b = new Button("" + i);
            add(b);
        }

        setSize(300, 100);
        setTitle("Number Buttons");
        setVisible(true);
    }

    public static void main(String[] args) {
        new NumberButtons();
    }
}
```



### 9. Write a program to generate KeyEvent when a key is pressed and display a “KeyPressed” message.
```java
import java.awt.*;
import java.awt.event.*;

public class KeyEventExample extends Frame implements KeyListener {

    Label label;

    KeyEventExample() {
        label = new Label("Press any key...", Label.CENTER);
        label.setBounds(50, 100, 200, 30);

        setTitle("KeyEvent Example");
        setSize(300, 200);
        setLayout(null);
        setVisible(true);

        addKeyListener(this);
        add(label);
        addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent e) {
                dispose();
            }
        });
    }

    public void keyTyped(KeyEvent e) {}

    public void keyPressed(KeyEvent e) {
        label.setText("KeyPressed: " + e.getKeyChar());
    }

    public void keyReleased(KeyEvent e) {}
    
    public static void main(String[] args) {
        new KeyEventExample();
    }
}
```
OR
```java
import java.awt.*;
import java.awt.event.*;

public class KeyEventExample extends Frame {

    Label label;

    KeyEventExample() {
        label = new Label("Press any key...", Label.CENTER);
        label.setBounds(50, 100, 200, 30);

        setTitle("KeyEvent Example");
        setSize(300, 200);
        setLayout(null);
        setVisible(true);

        add(label);

        addKeyListener(new KeyAdapter() {
            public void keyPressed(KeyEvent e) {
                label.setText("KeyPressed: " + e.getKeyChar());
            }
        });

        addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent e) {
                dispose();
            }
        });
    }

    public static void main(String[] args) {
        new KeyEventExample();
    }
}
```

### 10. Write a program using URL class to retrieve the host, protocol, port and file of the URL http://www.msbte.org.in.
```java
import java.net.*;

public class URLInfo {
    public static void main(String[] args) throws Exception {
        URL url = new URL("http://www.msbte.org.in");

        System.out.println("Protocol: " + url.getProtocol());
        System.out.println("Host: " + url.getHost());
        System.out.println("Port: " + url.getPort());
        System.out.println("File: " + url.getFile());
    }
}
```
