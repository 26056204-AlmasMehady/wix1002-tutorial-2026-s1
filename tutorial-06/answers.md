# Tutorial 06 Answers

## Question 1

### a. Static method to find the maximum of three integers

```java
public static int maximum(int a, int b, int c) {
    return Math.max(a, Math.max(b, c));
}
```

### b. Static method to check whether a number is a square number

```java
public static boolean isSquare(int number) {
    if (number < 0) {
        return false;
    }

    int root = (int) Math.sqrt(number);
    return root * root == number;
}
```

### c. Static method to calculate C(n, k)

```java
public static long combination(int n, int k) {
    if (k < 0 || k > n) {
        return 0;
    }

    long result = 1;
    for (int i = 1; i <= k; i++) {
        result = result * (n - i + 1) / i;
    }
    return result;
}
```

### d. Static method to check whether a number is pentagonal

```java
public static boolean isPentagonal(int number) {
    if (number <= 0) {
        return false;
    }

    for (int n = 1; ; n++) {
        int p = n * (3 * n - 1) / 2;

        if (p == number) {
            return true;
        }
        if (p > number) {
            return false;
        }
    }
}
```

### e. Static method to count letters and digits in a string

```java
public static void countLettersAndDigits(String text) {
    int letters = 0;
    int digits = 0;

    for (int i = 0; i < text.length(); i++) {
        char ch = text.charAt(i);

        if (Character.isLetter(ch)) {
            letters++;
        } else if (Character.isDigit(ch)) {
            digits++;
        }
    }

    System.out.println("Letters: " + letters);
    System.out.println("Digits: " + digits);
}
```

### f. Static void method to generate 10 random numbers from 0 to 100

The numbers are stored in the array passed to the method, so `main` can use them.

```java
public static void generateNumbers(int[] numbers) {
    for (int i = 0; i < 10; i++) {
        numbers[i] = (int) (Math.random() * 101);
    }
}
```

### g. Static method to get the area and circumference of a circle

This method returns both values in an array.

```java
public static double[] circleInfo(double radius) {
    double area = Math.PI * radius * radius;
    double circumference = 2 * Math.PI * radius;

    return new double[] {area, circumference};
}
```

### h. Static method to return the first random number from 0 to 10 that appears twice

```java
public static int firstRepeatedNumber() {
    boolean[] seen = new boolean[11];

    while (true) {
        int number = (int) (Math.random() * 11);

        if (seen[number]) {
            return number;
        }

        seen[number] = true;
    }
}
```

## Question 2

Write a program with a method that displays three numbers in decreasing order.

```java
public class DecreasingOrder {
    public static void displayDecreasing(int a, int b, int c) {
        int temp;

        if (a < b) {
            temp = a;
            a = b;
            b = temp;
        }

        if (a < c) {
            temp = a;
            a = c;
            c = temp;
        }

        if (b < c) {
            temp = b;
            b = c;
            c = temp;
        }

        System.out.println(a + " " + b + " " + c);
    }

    public static void main(String[] args) {
        displayDecreasing(5, 9, 2);
    }
}
```
