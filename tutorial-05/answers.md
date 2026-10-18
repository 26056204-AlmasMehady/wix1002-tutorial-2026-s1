# Tutorial 05 Answers

## Question 1

### a. Declare an array for 12 floating point numbers

```java
double[] numbers = new double[12];
```

### b. Initialize an array with A to E

```java
char[] letters = {'A', 'B', 'C', 'D', 'E'};
```

### c. Declare an array for 100 student names

```java
String[] names = new String[100];
```

### d. Declare a table with 6 rows and 2 columns

```java
int[][] table = new int[6][2];
```

### e. Initialize the array

```java
int[][] values = {
    {6, 9},
    {2, 5},
    {4, 6}
};
```

### f. Change the values of the array

```java
values[1][1] = 4;
values[2][0] = 3;
values[2][1] = 7;
```

### g. Display all values in contact on separate lines

```java
for (int i = 0; i < contact.length; i++) {
    System.out.println(contact[i]);
}
```

## Question 2

### a.

Use double quotes for strings.

```java
String[] code = {"AAA", "AAB", "AAC", "AAD"};
```

### b.

Use `new int[10]`, stop before `num.length`, and add each array element to `sum`.

```java
int[] num = new int[10];
for (int k = 0; k < num.length; k++) {
    sum += num[k];
}
```

### c.

The second dimension needs to be created before using `t[1][2]`.

```java
int[][] t = new int[3][3];
t[1][2] = 5;
```

### d.

The array has indexes 0 to 4, so `++i` makes the index 5 and causes an error. Use index 4.

```java
int i = 4;
int[] score = new int[5];
score[1] = 78;
score[i] = 100;
```

## Question 3

The final values of the array `marks` are:

```text
marks[0] = 961
marks[1] = 31
marks[2] = 1
marks[3] = 31
marks[4] = 31
```

## Question 4

Display the number of times the word `the` appears in `sentence`. This is case sensitive.

```java
int count = 0;

for (int i = 0; i < sentence.length; i++) {
    String[] words = sentence[i].split("\\\\s+");

    for (int j = 0; j < words.length; j++) {
        if (words[j].matches("[^\\\\w]*the[^\\\\w]*")) {
            count++;
        }
    }
}

System.out.println(count);
```

## Question 5

Display the array in reverse order and reverse each string too.

```java
for (int i = sentence.length - 1; i >= 0; i--) {
    for (int j = sentence[i].length() - 1; j >= 0; j--) {
        System.out.print(sentence[i].charAt(j));
    }
    System.out.println();
}
```

## Question 6

Generate a random number from 0 to 255, store its binary bits in an 8 element array, and display the bits.

```java
int number = (int)(Math.random() * 256);
int[] bits = new int[8];

for (int i = 7; i >= 0; i--) {
    bits[i] = number % 2;
    number = number / 2;
}

for (int i = 0; i < 8; i++) {
    System.out.print(bits[i]);
}
System.out.println();
```
