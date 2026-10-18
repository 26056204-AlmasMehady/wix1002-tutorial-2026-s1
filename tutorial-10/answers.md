# Tutorial 10 Answers

## Question 1

### DiscountPolicy class

```java
public abstract class DiscountPolicy {
    public abstract double computeDiscount(int count, double itemCost);
}
```

### BulkDiscount class

```java
public class BulkDiscount extends DiscountPolicy {
    private int minimum;
    private double discountRate;

    public BulkDiscount(int minimum, double discountRate) {
        this.minimum = minimum;
        this.discountRate = discountRate;
    }

    @Override
    public double computeDiscount(int count, double itemCost) {
        if (count > minimum) {
            return count * itemCost * discountRate;
        }
        return 0;
    }
}
```

### OtherDiscount class

```java
public class OtherDiscount extends DiscountPolicy {
    @Override
    public double computeDiscount(int count, double itemCost) {
        double rate;

        if (count <= 2) {
            rate = 0;
        } else if (count <= 5) {
            rate = 0.10;
        } else if (count <= 8) {
            rate = 0.20;
        } else {
            rate = 0.30;
        }

        return count * itemCost * rate;
    }
}
```

### combineDiscount class

```java
public class combineDiscount extends DiscountPolicy {
    private DiscountPolicy policy1;
    private DiscountPolicy policy2;

    public combineDiscount(DiscountPolicy policy1, DiscountPolicy policy2) {
        this.policy1 = policy1;
        this.policy2 = policy2;
    }

    @Override
    public double computeDiscount(int count, double itemCost) {
        double discount1 = policy1.computeDiscount(count, itemCost);
        double discount2 = policy2.computeDiscount(count, itemCost);

        return Math.max(discount1, discount2);
    }
}
```

### Tester class

```java
public class DiscountTester {
    public static void main(String[] args) {
        DiscountPolicy bulk = new BulkDiscount(5, 0.15);
        DiscountPolicy other = new OtherDiscount();
        DiscountPolicy combined = new combineDiscount(bulk, other);

        System.out.println("Bulk discount: " +
            bulk.computeDiscount(7, 10));
        System.out.println("Other discount: " +
            other.computeDiscount(7, 10));
        System.out.println("Best discount: " +
            combined.computeDiscount(7, 10));
    }
}
```

## Question 2

### Interest interface

```java
public interface Interest {
    double computeInterest();
}
```

### SavingAccount class

```java
public class SavingAccount implements Interest {
    private double balance;

    public SavingAccount(double balance) {
        this.balance = balance;
    }

    @Override
    public double computeInterest() {
        return balance * 0.005 / 12;
    }
}
```

### FixedAccount class

```java
public class FixedAccount implements Interest {
    private double balance;

    public FixedAccount(double balance) {
        this.balance = balance;
    }

    @Override
    public double computeInterest() {
        return balance * 0.03 / 12;
    }
}
```

### Tester class

```java
public class InterestTester {
    public static void main(String[] args) {
        Interest saving = new SavingAccount(1000);
        Interest fixed = new FixedAccount(1000);

        System.out.println("Saving monthly interest: " +
            saving.computeInterest());
        System.out.println("Fixed monthly interest: " +
            fixed.computeInterest());
    }
}
```

## Question 3

### Person class

```java
public class Person implements Comparable<Person> {
    private String name;

    public Person(String name) {
        this.name = name;
    }

    public String getName() {
        return name;
    }

    public void display() {
        System.out.println(name);
    }

    @Override
    public int compareTo(Person other) {
        return name.compareTo(other.name);
    }
}
```

### Tester class

```java
import java.util.Arrays;

public class PersonTester {
    public static void main(String[] args) {
        Person[] people = {
            new Person("Sara"),
            new Person("Adam"),
            new Person("John")
        };

        Arrays.sort(people);

        for (Person person : people) {
            person.display();
        }
    }
}
```
