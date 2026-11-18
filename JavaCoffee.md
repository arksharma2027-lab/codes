1. Division with Try-Catch (Exp. 10)
Question: Write a Java program to accept two integers and display their division. Handle division by zero using a try-catch block.

java
import java.util.Scanner;

public class DivisionTryCatch {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter first integer: ");
        int num1 = sc.nextInt();
        System.out.print("Enter second integer: ");
        int num2 = sc.nextInt();

        try {
            int result = num1 / num2;
            System.out.println("Division result: " + result);
        } catch (ArithmeticException e) {
            System.out.println("Error: Division by zero is not allowed!");
        } finally {
            sc.close();
        }
    }
}
2. User-Defined Exception: InvalidAgeException (Exp. 12)
Question: Write a Java program to define a user-defined exception InvalidAgeException. Accept the age from the user, throw the exception if age is less than 18, and catch it in main().

java
import java.util.Scanner;

class InvalidAgeException extends Exception {
    public InvalidAgeException(String message) {
        super(message);
    }
}

public class AgeValidator {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter your age: ");
        int age = sc.nextInt();

        try {
            if (age < 18) {
                throw new InvalidAgeException("Age must be 18 or above.");
            }
            System.out.println("You are eligible.");
        } catch (InvalidAgeException e) {
            System.out.println("Caught Exception: " + e.getMessage());
        } finally {
            sc.close();
        }
    }
}
3. Rectangle Area and Perimeter (Exp. 1)
Question: Write a Java program to accept the length and breadth of a rectangle from the user and calculate its area and perimeter using variables.

java
import java.util.Scanner;

public class RectangleCalc {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter length: ");
        double length = sc.nextDouble();
        System.out.print("Enter breadth: ");
        double breadth = sc.nextDouble();

        double area = length * breadth;
        double perimeter = 2 * (length + breadth);

        System.out.println("Area of Rectangle: " + area);
        System.out.println("Perimeter of Rectangle: " + perimeter);
        sc.close();
    }
}
4. FileWriter and FileReader (Exp. 13)
Question: Write a Java program to write the names of five students into a file using FileWriter, and then read and display the contents of the file using FileReader.

java
import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;

public class StudentFile {
    public static void main(String[] args) {
        String[] names = {"Alice", "Bob", "Charlie", "David", "Eva"};
        
        // Writing to file
        try (FileWriter fw = new FileWriter("students.txt")) {
            for (String name : names) {
                fw.write(name + "\n");
            }
            System.out.println("Data written successfully.");
        } catch (IOException e) {
            System.out.println("Error writing to file: " + e.getMessage());
        }

        // Reading from file
        try (FileReader fr = new FileReader("students.txt")) {
            int i;
            System.out.println("Contents of the file:");
            while ((i = fr.read()) != -1) {
                System.out.print((char) i);
            }
        } catch (IOException e) {
            System.out.println("Error reading file: " + e.getMessage());
        }
    }
}
5. Constructor Overloading (Exp. 4)
Question: Write a Java program to demonstrate constructor overloading using a Rectangle class with a default and a parameterized constructor.

java
class Rectangle {
    double length, breadth;

    // Default constructor
    public Rectangle() {
        this.length = 1.0;
        this.breadth = 1.0;
    }

    // Parameterized constructor
    public Rectangle(double length, double breadth) {
        this.length = length;
        this.breadth = breadth;
    }

    public void display() {
        System.out.println("Length: " + length + ", Breadth: " + breadth + ", Area: " + (length * breadth));
    }
}

public class ConstructorOverload {
    public static void main(String[] args) {
        Rectangle rect1 = new Rectangle();
        System.out.print("Default Rectangle: ");
        rect1.display();

        Rectangle rect2 = new Rectangle(5.0, 3.0);
        System.out.print("Parameterized Rectangle: ");
        rect2.display();
    }
}
6. BufferedReader (Exp. 14)
Question: Write a Java program to read a text file line by line using BufferedReader. Display each line with its line number and the total number of lines at the end.

java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class ReadWithLineNumbers {
    public static void main(String[] args) {
        int lineCount = 0;
        try (BufferedReader br = new BufferedReader(new FileReader("students.txt"))) { // Ensure this file exists
            String line;
            while ((line = br.readLine()) != null) {
                lineCount++;
                System.out.println(lineCount + ": " + line);
            }
            System.out.println("Total number of lines: " + lineCount);
        } catch (IOException e) {
            System.out.println("File not found or error reading: " + e.getMessage());
        }
    }
}
7. Single-Level Inheritance (Exp. 7)
Question: Write a Java program to demonstrate single-level inheritance with Person (name, age) and Employee (salary) classes. Display the details of one employee.

java
class Person {
    String name;
    int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
}

class Employee extends Person {
    double salary;

    public Employee(String name, int age, double salary) {
        super(name, age);
        this.salary = salary;
    }

    public void displayDetails() {
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("Salary: $" + salary);
    }
}

public class InheritanceDemo {
    public static void main(String[] args) {
        Employee emp = new Employee("John Doe", 30, 50000.0);
        emp.displayDetails();
    }
}
8. Multiple Catch Blocks (Exp. 11)
Question: Write a Java program that uses multiple catch blocks to handle ArithmeticException, ArrayIndexOutOfBoundsException, and NumberFormatException.

java
public class MultipleCatchDemo {
    public static void main(String[] args) {
        try {
            // Simulating NumberFormatException
            String str = "abc";
            int num = Integer.parseInt(str);
            
            // Simulating ArrayIndexOutOfBoundsException
            int[] arr = new int[5];
            arr[10] = 50;

            // Simulating ArithmeticException
            int result = 10 / 0;
            
        } catch (ArithmeticException e) {
            System.out.println("ArithmeticException caught: Cannot divide by zero.");
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("ArrayIndexOutOfBoundsException caught: Index is out of bounds.");
        } catch (NumberFormatException e) {
            System.out.println("NumberFormatException caught: Invalid number format.");
        }
    }
}
9. Method Overloading: Area (Exp. 8)
Question: Write a Java program to demonstrate method overloading by defining area() methods to calculate the area of a square and a rectangle.

java
class AreaCalculator {
    // Area of square
    public double area(double side) {
        return side * side;
    }

    // Area of rectangle
    public double area(double length, double breadth) {
        return length * breadth;
    }
}

public class MethodOverloading {
    public static void main(String[] args) {
        AreaCalculator calc = new AreaCalculator();
        
        System.out.println("Area of square (side=4): " + calc.area(4.0));
        System.out.println("Area of rectangle (length=5, breadth=3): " + calc.area(5.0, 3.0));
    }
}
10. AWT Frame with FlowLayout (Exp. 18 – part)
Question: Write a Java program to create an AWT Frame containing a Label and two Buttons arranged using FlowLayout.

java
import java.awt.*;
import java.awt.event.WindowAdapter;
import java.awt.event.WindowEvent;

public class AWTFlowLayout {
    public static void main(String[] args) {
        Frame frame = new Frame("AWT FlowLayout Example");
        frame.setLayout(new FlowLayout());

        Label label = new Label("This is a Label");
        Button btn1 = new Button("Button 1");
        Button btn2 = new Button("Button 2");

        frame.add(label);
        frame.add(btn1);
        frame.add(btn2);

        frame.setSize(300, 200);
        frame.setVisible(true);

        frame.addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent e) {
                System.exit(0);
            }
        });
    }
}
11. Scanner and Math (Exp. 6)
Question: Write a Java program to accept a number using java.util.Scanner and display its square root and cube using java.lang.Math.

java
import java.util.Scanner;

public class MathOperations {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a number: ");
        double num = sc.nextDouble();

        double sqrt = Math.sqrt(num);
        double cube = Math.pow(num, 3);

        System.out.println("Square root of " + num + " is: " + sqrt);
        System.out.println("Cube of " + num + " is: " + cube);
        
        sc.close();
    }
}
12. Interface Shape (Exp. 9)
Question: Write a Java program to define an interface Shape with the method area() and implement it in two classes, Circle and Rectangle.

java
interface Shape {
    double area();
}

class Circle implements Shape {
    double radius;

    public Circle(double radius) {
        this.radius = radius;
    }

    @Override
    public double area() {
        return Math.PI * radius * radius;
    }
}

class Rectangle implements Shape {
    double length, breadth;

    public Rectangle(double length, double breadth) {
        this.length = length;
        this.breadth = breadth;
    }

    @Override
    public double area() {
        return length * breadth;
    }
}

public class InterfaceDemo {
    public static void main(String[] args) {
        Shape circle = new Circle(5.0);
        Shape rectangle = new Rectangle(4.0, 6.0);

        System.out.println("Area of Circle: " + circle.area());
        System.out.println("Area of Rectangle: " + rectangle.area());
    }
}
13. AWT Login Form with GridLayout (Exp. 19 – part)
Question: Write a Java program to design an AWT login form with Labels, a Username TextField, a Password TextField (masked with '*') and a Login Button using GridLayout.

java
import java.awt.*;
import java.awt.event.WindowAdapter;
import java.awt.event.WindowEvent;

public class AWTLoginForm {
    public static void main(String[] args) {
        Frame frame = new Frame("Login Form");
        frame.setLayout(new GridLayout(3, 2, 10, 10));

        Label userLabel = new Label("Username:");
        TextField userText = new TextField();
        
        Label passLabel = new Label("Password:");
        TextField passText = new TextField();
        passText.setEchoChar('*');
        
        Button loginBtn = new Button("Login");
        Label emptyLabel = new Label(""); // Placeholder for alignment

        frame.add(userLabel);
        frame.add(userText);
        frame.add(passLabel);
        frame.add(passText);
        frame.add(loginBtn);
        frame.add(emptyLabel);

        frame.setSize(300, 200);
        frame.setVisible(true);

        frame.addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent e) {
                System.exit(0);
            }
        });
    }
}
14. Even Numbers using For Loop (Exp. 3)
Question: Write a Java program to print all even numbers between 1 and 50 using a for loop.

java
public class EvenNumbers {
    public static void main(String[] args) {
        System.out.println("Even numbers between 1 and 50:");
        for (int i = 1; i <= 50; i++) {
            if (i % 2 == 0) {
                System.out.print(i + " ");
            }
        }
    }
}
15. JDBC Select (Exp. 16 – part)
Question: Write a Java program to connect to the MySQL database StudentMan using JDBC and display all records of the Student table (roll_no, name, marks) using a ResultSet.
(Note: Requires mysql-connector-java dependency. Assumes DB credentials: root/password)

java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.Statement;

public class JDBCSelectDemo {
    public static void main(String[] args) {
        String url = "jdbc:mysql://localhost:3306/StudentMan";
        String user = "root";
        String password = "password";

        try {
            Class.forName("com.mysql.cj.jdbc.Driver");
            Connection con = DriverManager.getConnection(url, user, password);
            Statement stmt = con.createStatement();
            ResultSet rs = stmt.executeQuery("SELECT * FROM Student");

            System.out.println("Roll No | Name | Marks");
            System.out.println("------------------------");
            while (rs.next()) {
                int roll = rs.getInt("roll_no");
                String name = rs.getString("name");
                int marks = rs.getInt("marks");
                System.out.println(roll + " | " + name + " | " + marks);
            }
            con.close();
        } catch (Exception e) {
            System.out.println("Error: " + e.getMessage());
        }
    }
}
16. Maximum of 3 Numbers (Exp. 2)
Question: Write a Java program to find the maximum of three numbers accepted from the user using if-else.

java
import java.util.Scanner;

public class MaxOfThree {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter three numbers: ");
        int a = sc.nextInt();
        int b = sc.nextInt();
        int c = sc.nextInt();

        if (a >= b && a >= c) {
            System.out.println(a + " is the maximum.");
        } else if (b >= a && b >= c) {
            System.out.println(b + " is the maximum.");
        } else {
            System.out.println(c + " is the maximum.");
        }
        sc.close();
    }
}
17. Swing JFrame with Components (Exp. 20 – part)
Question: Write a Java program to create a Swing JFrame with a JLabel, JTextField, JCheckBox, JComboBox and a JButton added to the window.

java
import javax.swing.*;

public class SwingComponents {
    public static void main(String[] args) {
        JFrame frame = new JFrame("Swing Components Demo");
        frame.setLayout(new java.awt.FlowLayout());
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        JLabel label = new JLabel("Name:");
        JTextField textField = new JTextField(15);
        JCheckBox checkBox = new JCheckBox("Subscribe");
        String[] options = {"Option 1", "Option 2", "Option 3"};
        JComboBox<String> comboBox = new JComboBox<>(options);
        JButton button = new JButton("Submit");

        frame.add(label);
        frame.add(textField);
        frame.add(checkBox);
        frame.add(comboBox);
        frame.add(button);

        frame.setSize(300, 200);
        frame.setVisible(true);
    }
}
18. JDBC Update (Exp. 17 – part)
Question: Write a Java program to update the marks of a student in the Student table of the database StudentMan for a given roll number using JDBC, and display the number of rows updated.

java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;

public class JDBCUpdateDemo {
    public static void main(String[] args) {
        String url = "jdbc:mysql://localhost:3306/StudentMan";
        String user = "root";
        String password = "password";

        int targetRoll = 101;
        int newMarks = 95;

        try {
            Class.forName("com.mysql.cj.jdbc.Driver");
            Connection con = DriverManager.getConnection(url, user, password);
            
            String query = "UPDATE Student SET marks = ? WHERE roll_no = ?";
            PreparedStatement pstmt = con.prepareStatement(query);
            pstmt.setInt(1, newMarks);
            pstmt.setInt(2, targetRoll);

            int rowsAffected = pstmt.executeUpdate();
            System.out.println(rowsAffected + " row(s) updated successfully.");
            
            con.close();
        } catch (Exception e) {
            System.out.println("Error: " + e.getMessage());
        }
    }
}
19. User-defined Package (Exp. 5)
Question: Write a Java program to create a user-defined package mypack containing a simple class Greeting with a method show(), and use it in another class.

File 1: Greeting.java (in directory mypack)

java
package mypack;

public class Greeting {
    public void show() {
        System.out.println("Hello from the mypack package!");
    }
}
File 2: MainClass.java (in parent directory of mypack)

java
import mypack.Greeting;

public class MainClass {
    public static void main(String[] args) {
        Greeting g = new Greeting();
        g.show();
    }
}
(Compile with: javac mypack/Greeting.java MainClass.java)

20. File Copy with Character Streams (Exp. 15)
Question: Write a Java program to copy the contents of one file to another using character streams and display the number of characters copied.

java
import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;

public class FileCopy {
    public static void main(String[] args) {
        int charCount = 0;
        try (FileReader fr = new FileReader("source.txt"); 
             FileWriter fw = new FileWriter("destination.txt")) {
             
            int c;
            while ((c = fr.read()) != -1) {
                fw.write(c);
                charCount++;
            }
            System.out.println("File copied successfully.");
            System.out.println("Total characters copied: " + charCount);
            
        } catch (IOException e) {
            System.out.println("An error occurred: " + e.getMessage());
        }
    }
}
