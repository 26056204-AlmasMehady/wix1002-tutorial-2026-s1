# Tutorial 02 Answers

## Question 1

### a. In one line using multiple Java statements

```java
System.out.print("Faculty of ");
System.out.print("Computer Science and ");
System.out.print("Information Technology.");
```

### b. In multiple lines using one Java statement

```java
System.out.println("Faculty of");
System.out.println("Computer Science and");
System.out.println("Information Technology.");
```

## Question 2

```java
System.out.println("SDN - Software-defined networking");
```

## Question 3

### a.

```java
System.out.println("Java Programming");
```

### b.

```java
System.out.println("Introduction to Java!");
```

### c.

```java
System.out.println("\t is the horizontal tab character");
```

### d.

```java
System.out.println("Java is case sensitive!");
```

## Question 4

### a. Store a matric number

```java
String matricNumber;
```

### b. Store the value of pi

```java
double pi = Math.PI;
```

### c. Set M to false

```java
boolean M = false;
```

### d. Set P to 8800000000

```java
long P = 8800000000L;
```

### e. Set letter to U

```java
char letter = 'U';
```

### f. Declare a constant named PRO with the value Java

```java
final String PRO = "Java";
```

## Question 5

### a.

`AMOUNT` is a constant, so its value cannot be changed. The value should also be a number, not a string.

```java
double AMOUNT = 32.5;
AMOUNT += 10;
System.out.println("The amount is " + AMOUNT);
```

### b.

Java uses `String` with a capital S, and text should use double quotation marks.

```java
String chapter = "Summary";
System.out.println(chapter);
```

### c.

The increment statement is incorrect, and `num1` was not declared in the given code. One correction is:

```java
int num = 0;
num++;
int num1 = num;
```

### d.

`%f` is for a decimal number. Convert `num` to a double for this format.

```java
int num = 3000;
System.out.printf("%4.2f%n", (double) num);
```

### e.

The scanner should read input from `System.in`, not `System.out`.

```java
String contact;
Scanner keyboard = new Scanner(System.in);
contact = keyboard.nextLine();
```

Remember to import Scanner if this code is used in a full program:

```java
import java.util.Scanner;
```

## Question 6

Write a Java program to calculate the circumference of a circle using the diameter. The result is shown to three decimal places.

```java
import java.util.Scanner;

public class CircleCircumference {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.print("Enter diameter: ");
        double diameter = input.nextDouble();

        double circumference = Math.PI * diameter;

        System.out.printf("Circumference: %.3f%n", circumference);

        input.close();
    }
}
```

## Question 7

Write a Java program to convert inches to meters. One inch is 2.54 centimeters, and 100 centimeters is one meter.

```java
import java.util.Scanner;

public class InchesToMeters {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.print("Enter inches: ");
        double inches = input.nextDouble();

        double meters = inches * 2.54 / 100;

        System.out.printf("Meters: %.2f%n", meters);

        input.close();
    }
}
```
