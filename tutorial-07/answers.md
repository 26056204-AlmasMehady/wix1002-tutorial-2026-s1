# Tutorial 07 Answers

## Question 1

### a. Store 10 random integers in integer.txt

```java
import java.io.FileOutputStream;
import java.io.PrintWriter;
import java.io.IOException;

public static void writeIntegers() throws IOException {
    PrintWriter out = new PrintWriter(new FileOutputStream("integer.txt"));

    for (int i = 0; i < 10; i++) {
        int number = (int) (Math.random() * 1001);
        out.println(number);
    }

    out.close();
}
```

### b. Read the integers and display the largest

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public static void readIntegers() throws FileNotFoundException {
    Scanner input = new Scanner(new File("integer.txt"));
    int largest = Integer.MIN_VALUE;

    while (input.hasNextInt()) {
        int number = input.nextInt();
        System.out.println(number);

        if (number > largest) {
            largest = number;
        }
    }

    System.out.println("Largest integer: " + largest);
    input.close();
}
```

### c. Store 10 random integers in the binary file integer.dat

```java
import java.io.DataOutputStream;
import java.io.FileOutputStream;
import java.io.IOException;

public static void writeBinaryIntegers() throws IOException {
    DataOutputStream out =
        new DataOutputStream(new FileOutputStream("integer.dat"));

    for (int i = 0; i < 10; i++) {
        int number = (int) (Math.random() * 1001);
        out.writeInt(number);
    }

    out.close();
}
```

### d. Read the binary integers and display them and their average

```java
import java.io.DataInputStream;
import java.io.FileInputStream;
import java.io.EOFException;
import java.io.IOException;

public static void readBinaryIntegers() throws IOException {
    DataInputStream in =
        new DataInputStream(new FileInputStream("integer.dat"));

    int count = 0;
    int sum = 0;

    try {
        while (true) {
            int number = in.readInt();
            System.out.println(number);
            sum += number;
            count++;
        }
    } catch (EOFException e) {
        // The file has no more integers.
    }

    in.close();

    if (count > 0) {
        System.out.println("Average: " + (double) sum / count);
    }
}
```

## Question 2

### a.

Use escaped backslashes in the file path.

```java
PrintWriter out = new PrintWriter(
    new FileOutputStream("d:\\data\\matrix.txt"));
```

### b.

The statement is correct as written. It opens the file and closes it. If the intention is to write something, use `out.println(...)` before closing it.

```java
try {
    PrintWriter out = new PrintWriter(new FileOutputStream("data.txt"));
    out.println("Hello");
    out.close();
} catch (FileNotFoundException e) {
    System.out.println("Problem with file output");
}
```

### c.

`Scanner` does not have a `readInt()` method. Use `DataInputStream` to read an integer from a binary file.

```java
DataInputStream a = new DataInputStream(
    new FileInputStream("data.dat"));
int num = a.readInt();
a.close();
```

### d.

`ObjectOutputStream` does not have a `print()` method. Use `writeChar()`.

```java
ObjectOutputStream o = new ObjectOutputStream(
    new FileOutputStream("data.dat"));
o.writeChar('A');
o.close();
```

## Question 3

This program converts each character to an 8-bit ASCII value, saves the bits in `data.txt`, then reads the bits and converts them back to the sentence.

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.io.PrintWriter;
import java.io.IOException;
import java.util.Scanner;

public class SentenceBinary {
    public static void main(String[] args) throws IOException {
        Scanner input = new Scanner(System.in);

        System.out.print("Enter a sentence: ");
        String sentence = input.nextLine();

        PrintWriter out = new PrintWriter("data.txt");

        for (int i = 0; i < sentence.length(); i++) {
            String binary = String.format("%8s",
                Integer.toBinaryString(sentence.charAt(i))).replace(' ', '0');
            out.print(binary);
        }
        out.close();

        Scanner file = new Scanner(new File("data.txt"));
        String bits = file.nextLine();
        file.close();

        String result = "";
        for (int i = 0; i + 7 < bits.length(); i += 8) {
            int ascii = Integer.parseInt(bits.substring(i, i + 8), 2);
            result += (char) ascii;
        }

        System.out.println(result);
        input.close();
    }
}
```
