# Tutorial 08 Answers

## Question 1

### a. Define a class Student

```java
public class Student {
}
```

### b. Instance variable for contact number

```java
private String contactNumber;
```

### c. Constructor that sets contact number to null

```java
public Student() {
    contactNumber = null;
}
```

### d. Constructor that sets contact number from a parameter

```java
public Student(String contactNumber) {
    this.contactNumber = contactNumber;
}
```

### e. Accessor and mutator methods

```java
public String getContactNumber() {
    return contactNumber;
}

public void setContactNumber(String contactNumber) {
    this.contactNumber = contactNumber;
}
```

### f. Method to display the contact number

```java
public void displayContactNumber() {
    System.out.println(contactNumber);
}
```

### g. Create a Student object

```java
Student student1 = new Student();
```

### h. Change the contact number using the mutator

```java
student1.setContactNumber("0123456789");
```

### i. Create an object of Animal

```java
Animal animal1 = new Animal();
```

### j. Create an Animal object to represent a cat

```java
Animal cat = new Animal();
```

### k. Create a Number object with values 20 and 40

```java
Number number1 = new Number(20, 40);
```

## Question 2

### a. Define a class Digit

```java
public class Digit {
}
```

### b. Instance variable to store a number

```java
private int number;
```

### c. Constructor that assigns the parameter to number

```java
public Digit(int number) {
    this.number = number;
}
```

### d. Method to multiply the digits

```java
public int digitMultiplication() {
    int n = Math.abs(number);
    int result = 1;

    if (n == 0) {
        return 0;
    }

    while (n > 0) {
        result *= n % 10;
        n /= 10;
    }

    return result;
}
```

### e. Method to display the digit multiplication

```java
public void displayDigitMultiplication() {
    System.out.println(digitMultiplication());
}
```

### f. Tester class for 4567

```java
public class DigitTester {
    public static void main(String[] args) {
        Digit d = new Digit(4567);
        d.displayDigitMultiplication();
    }
}
```

## Question 3

Class for a 2D coordinate system.

```java
public class Coordinate {
    private double x;
    private double y;

    public Coordinate() {
        x = 0;
        y = 0;
    }

    public Coordinate(double x, double y) {
        this.x = x;
        this.y = y;
    }

    public double getX() {
        return x;
    }

    public double getY() {
        return y;
    }

    public void setX(double x) {
        this.x = x;
    }

    public void setY(double y) {
        this.y = y;
    }

    public void display() {
        System.out.println("x = " + x + ", y = " + y);
    }
}
```

## Question 4

The `pay` method is overloaded for the different payment types.

```java
public class Payment {
    public void pay(double amount) {
        System.out.println("Cash payment: " + amount);
    }

    public void pay(double amount, String chequeNumber) {
        System.out.println("Cheque payment: " + amount);
        System.out.println("Cheque number: " + chequeNumber);
    }

    public void pay(double amount, String cardHolderName,
                    String cardType, String expirationDate,
                    String validationCode) {
        System.out.println("Credit card payment: " + amount);
        System.out.println("Card holder: " + cardHolderName);
        System.out.println("Card type: " + cardType);
        System.out.println("Expiration date: " + expirationDate);
        System.out.println("Validation code: " + validationCode);
    }
}
```

## Question 5

The class counts connections. Each new object adds one connection, and disconnecting reduces the count.

```java
public class Connection {
    private static int connectionCount = 0;
    private boolean connected;

    public Connection() {
        connectionCount++;
        connected = true;
    }

    public void disconnect() {
        if (connected) {
            connectionCount--;
            connected = false;
        }
    }

    public void display() {
        System.out.println("Number of connections: " + connectionCount);
    }
}
```
