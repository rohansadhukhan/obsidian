##### What is Java ?

- High Level Language
- Java is a platform independent language
- Object Oriented Programming language
- Portable (WORA: Write Once, Run Anywhere)

### What are the main components of Java ?


JVM, JRE, and JDK are platform dependent, (different for MAC OS, WINDOWS, etc)

#### Java Virtual Machine (JVM)

It is a abstract machine (not physical machine, it is a software)

![[jvm.excalidraw|1000]]

JVM provides portability, because when java code compiled, it converted into **Byte Code**. This byte code can be run by JVM.
JVM has Just-In-Time (JIT) Compiler

#### Java Runtime Environment (JRE)

JRE consists of the Java Virtual Machine (JVM), core classes, and supporting libraries necessary for executing Java programs. Using JRE we can only run any Byte code of a Java code, but we can not write.

![[jre.excalidraw|1000]]

#### Java Development Kit (JDK)

The JDK includes the Java Runtime Environment (JRE), which is needed to run Java programs, along with additional development tools such as compilers, debuggers, and other utilities.

![[jdk|1000]]

#### Java Editions
##### Java Standard Edition (JSE)
Core Java
##### Java Enterprise Edition (JEE)
JSE + APIs (like transactional APIs Rollback, Commit, Persistence APIs manage relational DB), Serverlet, JSP
##### Java Micro/Mobile Edition (JME)
JSE + APIs for mobile application

