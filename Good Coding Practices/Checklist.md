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

-

    

    
    
