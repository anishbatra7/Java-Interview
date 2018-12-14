Read notes on phone – interview preparation.

**Lecture 6**  – Exceptions/ Debugging/Annotations/ Regex in Java. Checked and Unchecked. Throwing and catching Exceptions. Hierarchy when catching (order matters). Custom Exceptions (create your own exception type by extending Exception). Finally clause (always executes no matter exception is thrown or not).

Create your own AutoCloseable Interface and open in try for it close automatically.


e.g. – try(InputStream inputStream = new FileInputStream(path)) 

Debugging.

Annotations.

Creating your own annotations:

@Target(ElementType.METHOD)
@Retention(RetentionPolicy.RUNTIME)
public @interface Authorized{

String headerKey( ) default “Bearer”;
}

Regular expressions – Pattern and Matcher

**Lecture 7**  – Generics in Java. Why Generics? Code reuse, type safety. Generic types can be bounded by other generic types. 

Number <- Integer (normally works)

Echo<Number> <- Echo<Integer> (NOOOOOOOO)
Generic types are not reified; i.e., after compilation they are removed and not available at runtime. This is also called type erasure. 
Generic parameters can also be defined at a method level. ○ But not at a field level .
Remember that Echo<Integer> is not an instance of type Echo<Number> (whereas Integer is an instance of type Number)? Keep that in mind and look at the following code? Enters Wildcards!!!
We’ve made GiftPrinter take a Gift of generic type Object and as we know, Gift<Computer> does not extend from Gift<Object> 
What we want is the generically typed Gift which is the supertype of all other generically typed Gift types. In Java, this is called the wildcard type! 
Wildcard types can only be used on instances (not class or methods) 
You cannot do public class Type<?> { 
You cannot do public <?> void methodName() { 
You cannot do public ? methodName() { 
You can do public void methodName(Gift<?> gift) { 
Only objects can use wildcard type parameters (variables, method parameters, etc.). 

**Lecture 8**  – Collections in Java. Iterator – to traverse a collection. for-each loop. Before explaining what went wrong (exactly) here’s how to correctly remove from a Collection while iterating.
ListInterface – ArrayList, Set, Map. Queue, PriorityQueue

**Lecture 9**  – Producer/Consumer problem, Race Condition, Deadlock, Atomicity, Locks and Semaphores

**Lecture 10**  – Monitor, Monitors in Java, Threads in Java, the volatile keyword, Thread confinement, Synchronization mechanisms. Thread safe collections/ utilities

Executors – ScheduledExecutors, Executor, ExecutorService

**Lecture 11** – IO in Java. InputStream, OutputStream, FileInputStream, BufferedInputStream, Reader.

NIO – Non-blocking IO – buffers, channels, selectors

**Lecture 12**  – Java 8 key features – default, static interface methods. default interface – multiple inheritance resolution. Lambda expressions, functional interfaces (see Eclipse for examples). Method references (to do)

**Lecture 13**  – libraries, testing patterns – guava, jackson, mockito, JUnit testing 

Design patterns – builder pattern, singleton pattern
