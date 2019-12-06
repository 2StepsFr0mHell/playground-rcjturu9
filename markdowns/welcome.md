The goal of this playground is to learn some basic stuff about Dart. It is highly recommended to know the basics of Java to be able to complete this playground.

Here's the Java class we'd like to create in Dart:

```
class Bicycle {
        
    private int cadence;
    private int gear;
    private int speed;
        
    public Bicycle(int startCadence, int startSpeed, int startGear) {
        gear = startGear;
        cadence = startCadence;
        speed = startSpeed;
    }
        
    public int getCadence() {
        return cadence;
    }
        
    public void setCadence(int newValue) {
        cadence = newValue;
    }

    public int getGear() {
        return gear;
    }
        
    public void setGear(int newValue) {
        gear = newValue;
    }
        
    public int getSpeed() {
        return speed;
    }
        
    public void applyBrake(int decrement) {
        speed -= decrement;
    }
        
    public void speedUp(int increment) {
        speed += increment;
    }
    
    @Override
    public String toString() {
        return "current speed of bicycle is "+speed;
    }
}
```

This Java program instantiates a new bicycle and brakes:

```java runnable
// { autofold
import java.io.*;
//}

public class Main {

    public static void main (String[] args) {
        Bicycle bicycle = new Bicycle(0, 2, 0);
        System.out.println(bicycle.toString());
        System.out.println("Let's brake");
        bicycle.applyBrake(1);
        System.out.println(bicycle.toString());
    }

}
// { autofold
class Bicycle {
        
    private int cadence;
    private int gear;
    private int speed;
        
    public Bicycle(int startCadence, int startSpeed, int startGear) {
        gear = startGear;
        cadence = startCadence;
        speed = startSpeed;
    }
        
    public int getCadence() {
        return cadence;
    }
        
    public void setCadence(int newValue) {
        cadence = newValue;
    }
    
    public int getGear() {
        return gear;
    }
        
    public void setGear(int newValue) {
        gear = newValue;
    }
        
    public int getSpeed() {
        return speed;
    }
        
    public void applyBrake(int decrement) {
        speed -= decrement;
    }
        
    public void speedUp(int increment) {
        speed += increment;
    }
    
    @Override
    public String toString() {
        return "current speed of bicycle is "+speed;
    }
}
//}
```

# Create your first Dart class

## Define the Bicycle class

- Neither `main()` nor `Bicycle` should be declared as public, because all identifiers are public by default. Dart doesn't have keywords for `public`, `private`, or `protected`.

## Define the constructor

- Using `this` in a constructor's parameter list is a handy shortcut for assigning values to instance variables.

ex: 

```dart
class Name {
	String surname;

	Name(this.surname);
}
```

## Print the bicycle instance

ex: 

```dart
void main() {
	var name = Name("Bak");
	print(name);
}
```

- The `new` keyword became optional in Dart 2.

- No errors or warnings should appear, indicating that type inference is working, and that the analyzer infers that `var name = ...` defines a Name instance.
