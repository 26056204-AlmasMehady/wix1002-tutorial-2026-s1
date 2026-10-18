# Tutorial 09 Answers

## Question 1

### a. Method to check if Student and Teacher are from the same class

```java
public static boolean compare(Student s, Teacher t) {
    return s.getClass() == t.getClass();
}
```

### b. Method to check if Student belongs to a descendant class of Person

```java
public static boolean isClass(Student s) {
    return s instanceof Person && s.getClass() != Person.class;
}
```

## Question 2

### Organism class

```java
public class Organism {
    protected double initialSize;
    protected double growthRate;

    public Organism(double initialSize, double growthRate) {
        this.initialSize = initialSize;
        this.growthRate = growthRate;
    }
}
```

### Animal class

```java
public class Animal extends Organism {
    private double amountOfEating;

    public Animal(double initialSize, double growthRate,
                  double amountOfEating) {
        super(initialSize, growthRate);
        this.amountOfEating = amountOfEating;
    }

    public void display() {
        System.out.println("Initial size: " + initialSize);
        System.out.println("Growth rate: " + growthRate);
        System.out.println("Amount of eating needed: " + amountOfEating);
    }
}
```

## Question 3

### PaySystem class

```java
public class PaySystem {
    protected double payRate;
    protected double hours;

    public PaySystem(double payRate, double hours) {
        this.payRate = payRate;
        this.hours = hours;
    }

    public double totalPay(double hours) {
        return payRate * hours;
    }

    public void displayPayment() {
        System.out.println("Total payment: " + totalPay(hours));
    }
}
```

### RegularPay class

```java
public class RegularPay extends PaySystem {
    public RegularPay(double payRate, double hours) {
        super(payRate, hours);
    }
}
```

### SpecialPay class

```java
public class SpecialPay extends PaySystem {
    public SpecialPay(double payRate, double hours) {
        super(payRate, hours);
    }

    @Override
    public double totalPay(double hours) {
        return super.totalPay(hours) * 1.30;
    }
}
```

## Question 4

### PurchaseSystem class

```java
public class PurchaseSystem {
    protected String productCode;
    protected double unitPrice;
    protected int quantity;
    protected double totalPrice;

    public PurchaseSystem(String productCode, double unitPrice, int quantity) {
        this.productCode = productCode;
        this.unitPrice = unitPrice;
        this.quantity = quantity;
    }

    public double computeTotalPrice() {
        totalPrice = unitPrice * quantity;
        return totalPrice;
    }

    public void display() {
        System.out.println("Product code: " + productCode);
        System.out.println("Unit price: " + unitPrice);
        System.out.println("Quantity: " + quantity);
        System.out.println("Total price: " + computeTotalPrice());
    }
}
```

### SugarPurchase class

```java
public class SugarPurchase extends PurchaseSystem {
    private double sugarWeight;

    public SugarPurchase(String productCode, double unitPrice, int quantity,
                         double sugarWeight) {
        super(productCode, unitPrice, quantity);
        this.sugarWeight = sugarWeight;
    }

    @Override
    public double computeTotalPrice() {
        totalPrice = unitPrice * quantity * sugarWeight;
        return totalPrice;
    }
}
```
