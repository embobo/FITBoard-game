# unity-scripting-reference
Reference and reflections on aspects of unity's scripting component

## Contents

1. [Unity Loop Order of Execution](unity-loop-order-of-execution)
2. [Useful Design Patterns](design-pattern-use)

Unity Loop Order of Execution:

![not found](https://docs.unity3d.com/uploads/Main/monobehaviour_flowchart.svg)

### Design Patter Use

#### Issues
1. [Many Reused Objects or Expensive Objects - Object Pooling](Object Pooling)
2. [Overcomplicated Base Classes - Proxy](Proxy)
3. [Overcomplicated system that other classes need to use - Facade](Facade)

#### Object Pooling

//Insert later

#### Proxy

[Reference](https://sourcemaking.com/design_patterns/proxy)

**Problem:** A base class has many more methods than I need access to after initialization of the object.

I experienced a need for this when working with Microsoft's [`SerialPort`](https://msdn.microsoft.com/en-us/library/system.io.ports.serialport(v=vs.110).aspx) class. The `SerialPort` class provides many many MANY methods, most of which are useful only when setting up the port but never after setup. To protect the port and make it approachable from other classes I created a `SerialPortProxy` class. 

`SerialPortProxy` contains:
- a protected `SerialPort serialPort` object
- virtual `Init()` method for port setup
- public methods for access to useful post-setup methods such as `Open()` and `ReadLine()`

`SerialPortProxy` can then be inherited and its `Init()` overridden. The inheriting class uses the `Init()` method and protected access to the `serialPort` for setup. This allows the port to have methods such as `ReadLine()` publicly available while hiding methods such as the `BaudRate` setter.

It occurs to me that a builder for the proxy could be used. My use case required only one SerialPortProxy object and so I did not implement a builder. In future I may want to implement this use case with the help of a builder.

#### Facade

[Reference](https://sourcemaking.com/design_patterns/facade)

**Problem:** This design pattern became useful to me when creating a reading and parsing subsystem. My subsystem used a serial port for IO, a data container for the read values, and a parser to convert the raw input. Additionally, this system needed to have it's parsed data available for reading from other classes.

// Insert Later When fully implemented
