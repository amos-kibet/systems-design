### Singleton Pattern.

- Comes under creation pattern.
- The singleton pattern is a software design pattern that restricts the instantiation of a class to one "single" instance. This is useful when exactly one object is needed to coordinate actions across the system.
- Involves a single class which is responsible to create an object.
- Makes sure that only a single object gets created.
- This class provides a way to access its only object which can be accessed directly without need to instantiate the object of the class.

- The singleton design pattern solves problems by allowing it to:

  - Ensure that a class has only one instance.
  - Easily access the sole instance of a class.
  - Control its instantiation.
  - Restrict the number of instances.
  - Access a global variable

- The singleton design pattern describes how to solve such problems:
  - Hide the constructors of the class.
  - Define a public static operation (`getInstance()`) that returns the sole instance of the class.

#### How To.

> Make the constructor private of the class we intend to define as singleton.
> Ensure that only a single instance of a class exists and a global point of access to it exists.

#### Example.

##### Scenario.

- Let's say we want to model America's Airforce One plane in our software. There can only be one instance of Airfore One, hence Singleton Design Pattern is best suited for this operation.

##### Code.

```
public class AirforceOne {

    // The sole instance of the class
    private static AirforceOne onlyInstance;

    // Make the constructor private so it's only accessible to
    // members of the class.
    private AirforceOne() {
    }

    public void fly() {
        System.out.println("Airforce one is flying...");
    }

    // Create a static method for object creation
    public static AirforceOne getInstance() {

        // Only instantiate the object when needed.
        if (onlyInstance == null) {
          // Make the instantiation process thread-safe
            private static AirforceOne onlyInstance = new AirforceOne();
        }

        return onlyInstance;
    }
}

public class Client {

    public void main() {
        AirforceOne airforceOne = AirforceOne.getInstance();
        airforceOne.fly();
    }
}
```
