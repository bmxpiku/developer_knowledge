## "protected" access modifier

1. Use it when you need to do some internal stuff that is not exposed in 
public API but still needs to be overriden by subclasses.
2. You need to use the protected access modifier, when you want the descendant class to see the fields / methods 
of the super class, BUT you do not want other classes to see these.

- `protected` methods remain a part of the interface of your class.
