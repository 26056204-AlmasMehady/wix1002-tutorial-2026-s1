# Tutorial 03 Answers

## Question 1

### a. Determine whether 3 x 8 = 27

```java
if (3 * 8 == 27) {
    System.out.println("They are equal");
} else {
    System.out.println("They are not equal");
}
```

### b. Check whether an integer is odd or even

```java
if (num % 2 == 0) {
    System.out.println("Even");
} else {
    System.out.println("Odd");
}
```

### c. Check whether a character is a capital letter

```java
if (ch >= 'A' && ch <= 'Z') {
    System.out.println("Capital letter");
} else {
    System.out.println("Not a capital letter");
}
```

### d. Display two strings in alphabetical order, ignoring case

```java
if (s1.compareToIgnoreCase(s2) <= 0) {
    System.out.println(s1);
    System.out.println(s2);
} else {
    System.out.println(s2);
    System.out.println(s1);
}
```

### e. Use switch to display the day for a number from 0 to 6

```java
switch (day) {
    case 0: System.out.println("Sunday"); break;
    case 1: System.out.println("Monday"); break;
    case 2: System.out.println("Tuesday"); break;
    case 3: System.out.println("Wednesday"); break;
    case 4: System.out.println("Thursday"); break;
    case 5: System.out.println("Friday"); break;
    case 6: System.out.println("Saturday"); break;
    default: System.out.println("Invalid day");
}
```

## Question 2

### a.

Use `==` to compare two numbers.

```java
if (num1 == num2)
    System.out.println("Number 1 is equal to number 2.");
```

### b.

Compare the numbers separately using `&&`.

```java
if (x > y && x > z)
    System.out.println("x is the largest number");
```

### c.

Use `.equals()` to compare string contents, and use `else` without a condition.

```java
String s1, s2;
if (s1.equals(s2))
    System.out.println("They are equal strings.");
else
    System.out.println("They are not equal strings.");
```

### d.

In Java, use `||` for OR, put the condition in parentheses, and remove the semicolon after the condition.

```java
if (x > 0 || y > 0)
    System.out.println("Either x or y is positive");
```

## Question 3

Given `x = 9` and `y = 10`.

### a. Output

```text
#####
$$$$$
```

### b. Output

```text
#####
$$$$$
```

### c. Output

```text
*****
#####
```

### d. Output

```text
No output
```

## Question 4

Find the biggest number among three integers.

```java
if (a >= b && a >= c) {
    System.out.println(a);
} else if (b >= a && b >= c) {
    System.out.println(b);
} else {
    System.out.println(c);
}
```

## Question 5

Check whether a year is a leap year.

```java
if ((year % 4 == 0 && year % 100 != 0) || year % 400 == 0) {
    System.out.println("Leap year");
} else {
    System.out.println("Not a leap year");
}
```
