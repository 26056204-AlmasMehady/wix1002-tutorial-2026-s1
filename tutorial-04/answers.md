# Tutorial 04 Answers

## Question 1

### a. Find the largest integer n so that n cubed is less than 2000

```java
int n = 1;
while ((n + 1) * (n + 1) * (n + 1) < 2000) {
    n++;
}
System.out.println(n);
```

### b. Display the square of the first twelve integers starting from 1

```java
for (int i = 1; i <= 12; i++) {
    System.out.println(i * i);
}
```

### c. Display a 4 by 5 matrix using random numbers from 0 to 100

```java
for (int i = 0; i < 4; i++) {
    for (int j = 0; j < 5; j++) {
        int number = (int)(Math.random() * 101);
        System.out.print(number + "\t");
    }
    System.out.println();
}
```

### d. Compute the sum of numbers from 1 to a given number

```java
Scanner input = new Scanner(System.in);
System.out.print("Enter a number: ");
int n = input.nextInt();

int sum = 0;
for (int i = 1; i <= n; i++) {
    sum += i;
}
System.out.println("Sum = " + sum);
```

### e. Compute the sum of the series in two decimal places

```java
double sum = 0;
for (int i = 1; i <= 25; i++) {
    sum += (double) i / (26 - i);
}
System.out.printf("%.2f%n", sum);
```

## Question 2

### a.

The loop should decrease `x`, otherwise it keeps increasing.

```java
for (x = 10; x > 0; x--)
    sum += x;
```

### b.

A `do while` loop needs braces for multiple statements and a semicolon after the condition.

```java
do {
    x += 2;
    y += x;
    System.out.println(x + " and " + y);
} while (x < 100);
```

### c.

Use `=` to initialize variables, `&&` to combine conditions, and `+` to join output values.

```java
for (x = 1, y = 20; x < y; x++, y -= 2) {
    System.out.println(x + " " + y);
}
```

### d.

The value of `i` needs to change inside the loop. The condition `i == 10` will not happen while `i < 10`.

```java
i = 1;
while (i < 10) {
    i++;
}
System.out.println("Program End");
```

## Question 3

Display the first ten Fibonacci numbers.

```java
int first = 1;
int second = 1;

System.out.print(first + " " + second);

for (int i = 3; i <= 10; i++) {
    int next = first + second;
    System.out.print(" " + next);
    first = second;
    second = next;
}
System.out.println();
```

## Question 4

Display a string in reverse order.

```java
Scanner input = new Scanner(System.in);
System.out.print("Enter a string: ");
String text = input.nextLine();

for (int i = text.length() - 1; i >= 0; i--) {
    System.out.print(text.charAt(i));
}
System.out.println();
```

Remember to add this import if you use `Scanner` in a complete Java program:

```java
import java.util.Scanner;
```
