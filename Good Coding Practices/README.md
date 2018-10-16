# Java-Interview
Some good material to revise before a Java developer interview

### OOPS Pillars:

## Encapsulation:

**Access Privileges:**

- public
- no modifier (referred to as “default” or “package-private”) - *the (default or package-private) means accessible to the Class itself and everyone within the same package.*
- protected (subclasses can access protected variables - doesn't matter in same package or not!)
- private

**Available for placement on:**

- Class (except protected / private unless nested [ see chapter 5])
- Field
- Method

### Class Structure:

1. Class signature
2. Static variables
3. Static methods
4. Instance variables
5. Instance constructors
6. Instance methods

**Best Practices**

- Minimize static methods
- Hard to test / not overridable
- Prefer immutable instance variables
- Prefer fully encapsulated objects
- private instance variables with getter methods
- Marking Class variables as final makes them immutable
- Prefer this when at all possible. Makes reasoning about object state easier and (as we’ll
see later) makes reasoning about concurrency much easier.
---

### hashCode and equals implementation:

- if x and y are equals(), their hashCode() value should be same. If x and y are not equals() - *their hashCode value can still be same!*

- in the equals implementation - *always use getClass instead of instanceof*

### Method Invocation:

Java is CBV = call by value

○ parameters to method are copied to new value
○ method cannot change reference (but can change values associated with the reference!)


