# Checklist

- Methods should be *private* (whenever possible)

- variables in the class should be *private final* (whenever possible)
```
private final String name;

private final String secondary;
```
- when making constructors - better to give default value instead of *null*
```
private static final String defaultSecondary = "Anish";

    public FixMe(String name) {
        this(name, defaultSecondary);
    }

    public FixMe(String name, String secondary) {
        this.name = name;
        this.secondary = new FixMeToo(true).analyze(secondary);
    }
```
- Should give descriptive name to methods *(verb or a verb followed by nouns)* and variables *(nouns)*

- add getter for all the private variables

```
public String getName() {
        return name;
     }

public String getSecondary() {
		return secondary;
     }
```
- default values should *private static final* 
```
private static final String defaultSecondary = "Anish";
```
- use "extract methods" functionality of Eclipse formatter to make code more modular

- When creating abstract classes need to keep encapsulation in mind. What fields/methods do you want to expose to everyone, just subclasses or no one.

○ If everyone (and method as fields should rarely if ever be public) mark public
○ If just subclasses mark protected
○ If just used by abstract class mark private

```
public abstract class BodyOfWater {

    private final String name;
    private final double volume;
    private final int connectedWaterBodiesCount;
    private final double flow;
    
    // protected constructor - so sub-classes can access it 
    protected BodyOfWater(String name, double volume, int connectedWaterBodiesCount, double flow) {
        this.name = name;
        this.volume = volume;
        this.connectedWaterBodiesCount = connectedWaterBodiesCount;
        this.flow = flow;
    }

    public String getName() {
        return name;
    }

    public double getVolume() {
        return volume;
    }

    public int getConnectedWaterBodiesCount() {
        return connectedWaterBodiesCount;
    }

    public double getFlow() {
        return flow;
    }
}
```
This is the class which extends the above "abstract class"
```
public class Brook extends BodyOfWater {

    private final String notCommon;

    public Brook(String name, double volume, int connectedWaterBodiesCount, double flow, String notCommon) {
        super(name, volume, connectedWaterBodiesCount, flow);
        this.notCommon = notCommon;
    }

    public String getNotCommon() {
        return notCommon;
    }
}
```
- Take care of how you implement hashCode and equals

- Don't put constants in interface

- A good pattern is to first make an Interface then make an AbstractClass which implements that Interface and provide the common implementations then provide the ConcreteClasses. - [check this out - why abstract class is not forced to implement interfaces](https://stackoverflow.com/questions/197893/why-an-abstract-class-implementing-an-interface-can-miss-the-declaration-impleme)
 
```
I need to add something of a warning to these answers. Coupling the base class to the interface creates a force in the structure of that class. In your basic example, it's a no brainer that the two should be coupled, but that may not hold true in all cases.

Take Java's collection framework classes:

abstract class AbstractList
class LinkedList extends AbstractList implements Queue
The fact that the Queue contract is implemented by LinkedList did not push the concern into AbstractList.

What's the distinction between the two cases? The purpose of BaseWorker was always (as communicated by its name and interface) to implement operations in IWorker. The purpose of AbstractList and that of Queue are divergent, but a descenant of the former can still implement the latter contract.
```

For more info: https://softwareengineering.stackexchange.com/questions/163641/interfaces-on-an-abstract-class

    
    
