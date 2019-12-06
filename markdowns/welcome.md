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
        Bicycle bicycle = new Bicycle(0, 0);
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
    private int speed = 0;
        
    public Bicycle(int startCadence, int startGear) {
        gear = startGear;
        cadence = startCadence;
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

You can write your code here and run it.

```dart runable
class Bicycle {
}

void main() {
}
```

Follow all the steps below. If you don't manage to make it work, you can still check the solution at the end of the playground.

## Define the Bicycle class

```dart
class MyClass {
  int myPublicInt;
  String myPublicString;
  int _myPrivateInt;
}

void main() {
}
```

- Neither `main()` nor `myClass` should be declared as public, because all identifiers are public by default. Dart doesn't have keywords for `public`, `private`, or `protected`.

- To mark a Dart identifier as private to its library, start its name with an underscore (`_`).

- By default, Dart provides implicit getters and setters for all public instance variables. You don't need to define your own getters/setters unless you want to enforce read-only or write-only variables, compute or verify a value, or update a value elsewhere.

## Define the constructor

```dart
MyClass(this.myPublicInt, this.myPublicString);
```

- Using `this` in a constructor's parameter list is a handy shortcut for assigning values to instance variables.

## Instantiate and print a bicycle instance

```dart
void main() {
  var bob = new MyClass(2, "bob");
  print(bob);
}
```

- The `new` keyword became optional in Dart 2.

- The output should show:

```dart
Instance of `MyClass`
```

No errors or warnings should appear, indicating that type inference is working, and that the analyzer infers that `var bob = ...` defines a MyClass instance. 

## Improve the output

```dart
@override
String toString() => 'my message $variableName';
```

- All Dart classes have a `toString()` method that you can override to provide more useful output.

- The `@override` annotation tells the analyzer that you are intentionally overriding a member. The analyzer raises an error if you've failed to perform the override properly.

- Dart supports single or double quotes when specifying strings.

- Shorten one-line functions or methods using fat arrow (`=>`) notation.

- Use string interpolation to put the value of an expression inside a string literal: `${expression}`. If the expression is an identifier, you can skip the braces: `$variableName`.

## Solution

```dart runnable
class Bicycle {
  int cadence;
  int _speed = 0;
  int get speed => _speed;
  int gear;

  Bicycle(this.cadence, this.gear);

  void applyBrake(int decrement) {
    _speed -= decrement;
  }

  void speedUp(int increment) {
    _speed += increment;
  }

  @override
  String toString() => 'Bicycle: $_speed mph';
}

void main() {
  var bike = Bicycle(2, 1);
  print(bike);
}
```


