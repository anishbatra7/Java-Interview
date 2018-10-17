# Homework mistakes

### Homework 1:

None

### Homework 2: (read more about bit operations)

- Spacing: *four blank spaces per indent.*

- Make methods private whenever possible.

Not a good practice:
```
public static int[] hexadecimalIntegerToBinary(int hex){

}
```
### Homework 3:

- whenever making a new variable - think of whether it can be *private final* or not. If yes, do that. Good practice.

- In the constructors - *better to give a default value instead of null*

Not a good practice:
```
public FixMe(String name) {
    this(name, null);
}
```         

- Don't forget to add getters for *private* methods.

- *static* is used along with *final* a lot of times - so **think about it**

Like here: it should be static final 

```
private static String defaultName = "Anish";
```

- Create more methods to increase the readibility! (use extract method in Eclipse).

### Homework 4: (read about varargs from slides)

- *private final* issue again.

- dont't forget to add annotations: for eg. @override

- in hashCode implementation: *should compare all instance field, and null check for getName().*

- Comment: no use of inheritance in terms of implementing and storing instance variables (like name).

### Homework 5: (read more about callback function implementation - using anonymous inner class)

- shouldn't loop and continue to call the timeMachine. Instead, should recur within the callback. 

Why this is bad practice?

```
public interface TimeTraveler {

static final double YEAR_LENGTH_IN_DAYS = 365.25d;
     
static final double DAY_LENGTH_IN_HOURS = 24d;

// some methods declaration
}
```

It's not a good practice to put constants in the interface. You can refer to https://stackoverflow.com/questions/2659593/what-is-the-use-of-interface-constants for more information.

- Ideally should make an abstract class to share code across all TimeTravelers. And for DoubleTimeTraveller, should extends the Linear since they share most code. 

- From lecture 5 slides:

*A good pattern is to first make an Interface then make an AbstractClass which implements that Interface and provide the common implementations then provide the ConcreteClasses.*
