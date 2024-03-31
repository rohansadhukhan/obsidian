There are two types of memory which JVM creates and store in RAM
- Stack
- Heap

### Stack Memory
- store temporary variable and separate memory block for methods
- store primitive data types
- store reference of the heap objects
	- strong reference
	- weak reference
	- soft reference
- each thread has its own stack memory, but they all share a common heap memory
- variables within a SCOPE is only visible and as soon as any variable goes OUT of the SCOPE, it get deleted from the stack in LIFO.
- when the stack memory goes full, it throws `java.lang.StackOverflowError`
- 

### Heap Memory
- object 


```java
public class MemoryManagement {
	public static void main(String[] args) {
		int primitiveVariable1 = 10;
		Person personObj1 = new Person();
		String stringLiteral1 = "11";
		MemoryManagement memObj = new MemoryManagement();
		memObj.memoryManagementTest(personObj);
	}

	private void memoryManagementTest(Person personObj) {
		Person personObj2 = personObj;
		String stringLiteral2 = "11";
		String stringLiteral3 = new String("11");
	}
}
```

![[memory_management.excalidraw|700]]




![[heap_memory.excalidraw|700]]





