# Week 2: How to Java Work

1.  JDK, JVM, và JRE khác nhau như thế nào? Vai trò của từng thành phần trong hệ sinh thái Java?

    Answer:

    - JVM: Java virtual machine is a virtual machine that complies bytecode(.class) into machine code which is suitable for operating system and hardward of laptop.
      It is dependent on operating system, and every OS need their own JVM to interact with system.
    - JRE: Java runtime environment is a collections of too that allow users run Java application on their laptops
      JRE = JVM + Java library + support tools.
    - JDK : is toolkit designged for Java developers. It includes everything needed to write ,complie, and run Java programs.
      JDK includes JRE

2.  JDK có những công cụ nào quan trọng cho lập trình viên Java?

    Answer:is toolkit designed for Java developers. It includes everything needed to write ,complie, and run Java programs.It includes Javac(Java Complier) - convert Java source code(.java)
    into bytecode(.class) then JVM execute them.

3.  JVM hoạt động như thế nào khi bạn chạy một chương trình Java?

    Answer:

    - Firstly, javac complier converts the java.file into a .clas file containing bytecode- an intermidiate code that the JVM can understand.
    - Then , JVM excecute the program

    * Class Loader loads and locates the .class into the memory
    * Bytecode verifier checks the bytecode if there are any errors
    * Interpreter & JIT complier convert bytecode into machine code that CPU can execute.JIT speeds up execution by converting frequently used code into machine code more eficiently
    * Gabage Collector cleans up unused objects to free up space

    - As a result, the program prints the result on the screen

4.  Có những thành phần quan trọng nào bên trong JVM?

    Answer:There are 3 parts in JVM:

    - Class loader

    * To load file .class into memory(RAM)
    * Manage class loading including Java built-in classes and user-defined class

    - Runtime Data Area (JVM Memory)

    * This part is divided into 5 smaller parts:
      Method Area: stores class metadata, static variables, and complied method code
      Heap: stores objects created with new, manged by GC to remove unused objects
      Stack:stores method's local variables, data used for caculations, method execution details
      PC Register: holds the address of the currently executing instruction for each thread
      Native method stack: used for calling native (non-Java method) often written in C/C++

    - Execution engine

    * Convert bytecode into machine code for execution: interpreter(translate and executes bytecode line by line) and JIT comlier- convert
      entire methods into machine code for reuse.

    - Garbage collector: use to free up unused object from the Heap.

5.  JVM quản lý bộ nhớ như thế nào? Các vùng nhớ quan trọng trong JVM là gì?

    Answer:
    This part is divided into 5 smaller parts:
    Method Area: stores class metadata, class structure and static variables, and complied method code
    Heap: stores objects created with new, manged by GC to remove unused objects
    Stack:stores method's local variables, data used for caculations, method callscalls
    PC Register: holds the address of the currently executing instruction for each thread
    Native method stack: used for calling native (non-Java method) often written in C/C++

6.  Class Metadata (Method Area) trong JVM có vai trò gì?

    Answer: this class is responsibility for storing class structure, metadata and static variablesvariables

7.  PermGen và Metaspace khác nhau như thế nào? Tại sao Java chuyển từ PermGen sang Metaspace từ Java 8?

    Answer: permgen has fixed memory and metaspace has dynamic one.

8.  Heap và Stack trong JVM khác nhau như thế nào?

    Answer:
    Heap :

    - store objects created using new, instance variable(fields of objects in constructor) and String literals (String PoolPool)
    - Larger and slower that stack but allows dynamic memmory allocation
    - Object exists until GC removes them
      Stack:
    - store methods calls, local variables and references to objects(but objects are in heap)
    - Small , fast and managed automaticlly(Last in first out)
    - Memory is freed when the method finishesfinishes

9.  Garbage Collection trong JVM là gì? Tại sao nó quan trọng?

    Answer: is the process of automatically reclaiming memory by removing objects that are no longer in use
    This helps prevent memory leak, reduce manual works ( unlike C,C++, Java does not require manual memory management- malloc(),free()) and ensures efficient memory management.

10. Những thuật toán chính của Garbage Collection mà JVM sử dụng là gì?

    Answer: -Mark and Sweep - Copying

11. JVM có những loại Garbage Collector nào? Khác nhau ở điểm nào?

    Answer:

12. Sự khác biệt giữa Minor GC, Major GC và Full GC là gì?

    Answer:
    Minor GC: run in young generation when Eden is full, surviving objects are moved to the Old generation,very fast
    Major GC: run in old generation when old generation is full , JVm collects garbage in this region, slower than Minor GC
    Full GC: run in entire heap when memory is nearly full , very slow

13. Bộ nhớ Stack có bị thu hồi bởi Garbage Collector không? Nếu không, nó được quản lý như thế nào?

    Answer:No, stack memory is not managed by the GC. It is managed automacticly by JVM

    - Each thread has its own stack, which is created when thread starts
    - when a method is called, a new stack frame is pushed onto the stack
    - when the method finishes, its stack fram is automaticlly removed
    - one a thread completes, its entire stack is destroyed

14. Làm thế nào để tránh Memory Leak trong Java?

    Answer: Always close resources , avoid static reference to large objects,

15. JIT Compiler trong JVM là gì? Nó cải thiện hiệu năng như thế nào?

    Answer:The JIT Compiler is a part of the JVM that converts bytecode into native machine code at runtime. This makes Java programs run much faster than interpreting bytecode line by line.
    JIT does not compile all code immediately but it monitors frequently executed hot and compile it to native code for better performance

16. Khi nào JIT Compiler dịch mã bytecode sang mã máy thực thi?

    Answer: JIT comlier translates bytecode into machine code at runtime. However, it doesn't complie everything immediately,
    instead JVM first interprets the bytecode, if a method is executed frequetnly JVM marks it as hot and compiles it into optimized machine code
    Future executions of this method use the complied native code, making it faster

17. Khi ứng dụng Java chạy chậm, bạn sẽ kiểm tra gì đầu tiên?

    Answer:

18. Làm thế nào để debug lỗi liên quan đến bộ nhớ Heap và Stack?

        Answer:
