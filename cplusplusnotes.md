## Chapter 1: Getting Started 
### 1.1 Hello World!

    #include <iostream> // preprocessor directive includes the content of std c++ lib iostream that contains std input and output streams.
    
    int main()          // entry point which is called upon the start of the program must always return int type which is the exit code of the program
    {
    
        std::cout << "Hello World!\n"; // cout is std output stream from iostream lib that prints Hello World. 
                                       // The << (stream insertion operator) inserts "Hello  World!" string literal into the stream object.
        return 0;
    }

### 1.2 Function
**function** represents sequence of staements to perform a specific task. It can accept arguments and return a single value (or not).
**function declaration** declares the existence of a function by specifying **type signature**. It has to be declared first before calling the function.
    
    int my_function(double arg) // return (int), function name and arguments (arg) are specified.

**function definition** is similar with **function declaration** that contains the sequece of statements that will be execute during function call.
**function** can also be a member of a class hence the name of its class is also part of the function type

    int My_class::member_function(char arg)
**function** can be defined with the same name but should have different argument types. This is called **function overloading**.

    int my_function(int arg)                // OK function overloading
    int my_function(char arg)               // OK function overloading
    int my_function(double arg1, int arg2)  // ERROR ambiguous
    int my_function(int arg1, double arg2)  // ERROR ambiguous
**default parameters**
    


### Initialization 
using = or {}
    
    double d = 2.3 or double d {2.3}  
**auto** can deduce type from intializer, avoiding long type name.
    
    auto d = 2.3 or auto d {2.3}
    
### Constants 
**const** immutability or cannot be modified and value can be calculated at runtime.
**constexpr** to specify constants or read only and value must be calculated at compile time
    [>c11]
    constexpr int v = 5 
    const int v = abs(5)      // OK evaluated at runtime.
    constexpr int v = abs(5)  // ERROR abs() is not a constexpr must be calculated at runtime.    

inside a struct it has to be static (or else a compile error) because it is true for all instances of the struct.

    struct person
    {
      static constexpr char name[] = "Juan Dela Cruz";
      static constexpr char* fisrt_letter_of_name = &name[0];
    }

 
**constexpr** functions 
