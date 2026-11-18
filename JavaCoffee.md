

Here are the shortened, simplified codes formatted cleanly in Markdown. 



\---



\### 1. Division with Try-Catch (Exp. 10)

```java

import java.util.\*;



class Div {

&#x20;   public static void main(String\[] a) {

&#x20;       Scanner s = new Scanner(System.in);

&#x20;       try {

&#x20;           System.out.println(s.nextInt() / s.nextInt());

&#x20;       } catch (ArithmeticException e) {

&#x20;           System.out.println("Cannot divide by zero");

&#x20;       }

&#x20;   }

}

```



\---



\### 2. User-Defined Exception: InvalidAgeException (Exp. 12)

```java

import java.util.\*;



class InvalidAgeException extends Exception { 

&#x20;   InvalidAgeException(String m) { super(m); } 

}



class Age {

&#x20;   public static void main(String\[] a) {

&#x20;       int age = new Scanner(System.in).nextInt();

&#x20;       try {

&#x20;           if (age < 18) throw new InvalidAgeException("Under 18!");

&#x20;           System.out.println("Eligible");

&#x20;       } catch (InvalidAgeException e) {

&#x20;           System.out.println("Caught: " + e.getMessage());

&#x20;       }

&#x20;   }

}

```



\---



\### 3. Rectangle Area and Perimeter (Exp. 1)

```java

import java.util.\*;



class Rect {

&#x20;   public static void main(String\[] a) {

&#x20;       Scanner s = new Scanner(System.in);

&#x20;       double l = s.nextDouble(), b = s.nextDouble();

&#x20;       System.out.println("Area: " + (l \* b) + ", Perimeter: " + (2 \* (l + b)));

&#x20;   }

}

```



\---



\### 4. FileWriter and FileReader (Exp. 13)

```java

import java.io.\*;



class FileIO {

&#x20;   public static void main(String\[] a) throws Exception {

&#x20;       try (FileWriter fw = new FileWriter("s.txt")) { fw.write("A\\nB\\nC\\nD\\nE"); }

&#x20;       try (FileReader fr = new FileReader("s.txt")) {

&#x20;           int c; 

&#x20;           while ((c = fr.read()) != -1) System.out.print((char) c);

&#x20;       }

&#x20;   }

}

```



\---



\### 5. Constructor Overloading (Exp. 4)

```java

class Rect {

&#x20;   Rect() { System.out.println("Default Area: 0"); }

&#x20;   Rect(int l, int b) { System.out.println("Param Area: " + (l \* b)); }

}



class Main {

&#x20;   public static void main(String\[] a) { 

&#x20;       new Rect(); 

&#x20;       new Rect(5, 3); 

&#x20;   }

}

```



\---



\### 6. BufferedReader with Line Numbers (Exp. 14)

```java

import java.io.\*;



class BR {

&#x20;   public static void main(String\[] a) throws Exception {

&#x20;       int c = 0; String l;

&#x20;       BufferedReader br = new BufferedReader(new FileReader("s.txt"));

&#x20;       while ((l = br.readLine()) != null) System.out.println(++c + ": " + l);

&#x20;       System.out.println("Total lines: " + c);

&#x20;   }

}

```



\---



\### 7. Single-Level Inheritance (Exp. 7)

```java

class Person { 

&#x20;   String n; int a; 

&#x20;   Person(String n, int a) { this.n = n; this.a = a; } 

}



class Emp extends Person {

&#x20;   double s;

&#x20;   Emp(String n, int a, double s) { super(n, a); this.s = s; }

&#x20;   public String toString() { return n + " " + a + " " + s; }

}



class Main {

&#x20;   public static void main(String\[] a) { System.out.println(new Emp("John", 30, 5000)); }

}

```



\---



\### 8. Multiple Catch Blocks (Exp. 11)

```java

class MultiCatch {

&#x20;   public static void main(String\[] a) {

&#x20;       try { 

&#x20;           int x = 10 / 0; 

&#x20;       } catch (ArithmeticException e) { 

&#x20;           System.out.println("Arithmetic Error"); 

&#x20;       } catch (ArrayIndexOutOfBoundsException e) { 

&#x20;           System.out.println("Array Error"); 

&#x20;       } catch (NumberFormatException e) { 

&#x20;           System.out.println("Number Format Error"); 

&#x20;       }

&#x20;   }

}

```



\---



\### 9. Method Overloading: Area (Exp. 8)

```java

class Area {

&#x20;   int area(int s) { return s \* s; }

&#x20;   int area(int l, int b) { return l \* b; }

&#x20;   

&#x20;   public static void main(String\[] a) {

&#x20;       Area o = new Area();

&#x20;       System.out.println(o.area(4) + " " + o.area(5, 3));

&#x20;   }

}

```



\---



\### 10. AWT Frame with FlowLayout (Exp. 18 – part)

```java

import java.awt.\*;



class AWTFlow {

&#x20;   public static void main(String\[] a) {

&#x20;       Frame f = new Frame("Flow");

&#x20;       f.setLayout(new FlowLayout());

&#x20;       f.add(new Label("Label")); f.add(new Button("B1")); f.add(new Button("B2"));

&#x20;       f.setSize(250, 150); f.setVisible(true);

&#x20;   }

}

```



\---



\### 11. Scanner and Math (Exp. 6)

```java

import java.util.\*;



class MathOp {

&#x20;   public static void main(String\[] a) {

&#x20;       double n = new Scanner(System.in).nextDouble();

&#x20;       System.out.println("Sqrt: " + Math.sqrt(n) + ", Cube: " + Math.pow(n, 3));

&#x20;   }

}

```



\---



\### 12. Interface Shape (Exp. 9)

```java

interface Shape { double area(); }



class Circle implements Shape { 

&#x20;   double r; 

&#x20;   Circle(double r) { this.r = r; } 

&#x20;   public double area() { return Math.PI \* r \* r; } 

}



class Rect implements Shape { 

&#x20;   double l, b; 

&#x20;   Rect(double l, double b) { this.l = l; this.b = b; } 

&#x20;   public double area() { return l \* b; } 

}



class Main {

&#x20;   public static void main(String\[] a) { 

&#x20;       System.out.println(new Circle(5).area() + " " + new Rect(4, 5).area()); 

&#x20;   }

}

```



\---



\### 13. AWT Login Form with GridLayout (Exp. 19 – part)

```java

import java.awt.\*;



class Login {

&#x20;   public static void main(String\[] a) {

&#x20;       Frame f = new Frame("Login"); f.setLayout(new GridLayout(3, 2));

&#x20;       f.add(new Label("User:")); f.add(new TextField());

&#x20;       f.add(new Label("Pass:")); 

&#x20;       TextField t = new TextField(); t.setEchoChar('\*'); f.add(t);

&#x20;       f.add(new Button("Login")); f.add(new Label(""));

&#x20;       f.setSize(250, 150); f.setVisible(true);

&#x20;   }

}

```



\---



\### 14. Even Numbers using For Loop (Exp. 3)

```java

class Even {

&#x20;   public static void main(String\[] a) {

&#x20;       for (int i = 2; i <= 50; i += 2) System.out.print(i + " ");

&#x20;   }

}

```



\---



\### 15. JDBC Select (Exp. 16 – part)

\*(Requires MySQL JDBC Driver)\*

```java

import java.sql.\*;



class Sel {

&#x20;   public static void main(String\[] a) throws Exception {

&#x20;       Connection c = DriverManager.getConnection("jdbc:mysql://localhost:3306/StudentMan", "root", "pass");

&#x20;       ResultSet r = c.createStatement().executeQuery("SELECT \* FROM Student");

&#x20;       while (r.next()) System.out.println(r.getInt(1) + " " + r.getString(2) + " " + r.getInt(3));

&#x20;       c.close();

&#x20;   }

}

```



\---



\### 16. Maximum of 3 Numbers (Exp. 2)

```java

import java.util.\*;



class Max {

&#x20;   public static void main(String\[] a) {

&#x20;       Scanner s = new Scanner(System.in);

&#x20;       int x = s.nextInt(), y = s.nextInt(), z = s.nextInt();

&#x20;       if (x >= y \&\& x >= z) System.out.println(x);

&#x20;       else if (y >= x \&\& y >= z) System.out.println(y);

&#x20;       else System.out.println(z);

&#x20;   }

}

```



\---



\### 17. Swing JFrame Components (Exp. 20 – part)

```java

import javax.swing.\*;



class Sw {

&#x20;   public static void main(String\[] a) {

&#x20;       JFrame f = new JFrame(); f.setLayout(new java.awt.FlowLayout());

&#x20;       f.add(new JLabel("L")); f.add(new JTextField(5)); f.add(new JCheckBox("C"));

&#x20;       f.add(new JComboBox<>(new String\[]{"A", "B"})); f.add(new JButton("B"));

&#x20;       f.setSize(300, 200); f.setVisible(true); f.setDefaultCloseOperation(3);

&#x20;   }

}

```



\---



\### 18. JDBC Update (Exp. 17 – part)

```java

import java.sql.\*;



class Upd {

&#x20;   public static void main(String\[] a) throws Exception {

&#x20;       Connection c = DriverManager.getConnection("jdbc:mysql://localhost:3306/StudentMan", "root", "pass");

&#x20;       int rows = c.createStatement().executeUpdate("UPDATE Student SET marks=95 WHERE roll\_no=1");

&#x20;       System.out.println("Updated rows: " + rows);

&#x20;       c.close();

&#x20;   }

}

```



\---



\### 19. User-defined Package (Exp. 5)

\*\*File 1: `Greeting.java`\*\* (inside folder `mypack`)

```java

package mypack;

public class Greeting { public void show() { System.out.println("Hello"); } }

```



\*\*File 2: `Main.java`\*\* (outside folder)

```java

import mypack.Greeting;

class Main { public static void main(String\[] a) { new Greeting().show(); } }

```



\---



\### 20. File Copy with Character Streams (Exp. 15)

```java

import java.io.\*;



class Copy {

&#x20;   public static void main(String\[] a) throws Exception {

&#x20;       FileReader r = new FileReader("a.txt"); FileWriter w = new FileWriter("b.txt");

&#x20;       int c, count = 0; 

&#x20;       while ((c = r.read()) != -1) { w.write(c); count++; }

&#x20;       r.close(); w.close(); 

&#x20;       System.out.println("Chars copied: " + count);

&#x20;   }

}

```

