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
**function declaration** declares the existence of a function by specifying **type signature**. It has to be declared (usually in the header .hpp files) first before calling the function. 
    
    int my_function(int arg) // return (int), function name and arguments (arg) are specified.

**function definition** is similar with **function declaration** except that it also contains the sequece of statements that will be execute during function call. The full definition can be found usually in the source (.cpp) files.

    int my_function(int arg)
    {
        // sequence of staments that are executed when this function is called.
        if (arg = 5)
            return arg;
        else
            ret 1;
    }

**function** can also be a member of a class hence the name of its class is also part of the function type

    int My_class::member_function(char arg)
    
**function** can be defined with the same name but should have different argument types. This is called **function overloading**.

    int my_function(int arg)                // OK function overloading
    int my_function(char arg)               // OK function overloading
    
    // ERROR ambiguous call because compiler does not refer to arguments arrangements of the function signature
    int my_function(double arg1, int arg2)  // ERROR ambiguous call
    int my_function(int arg1, double arg2)  // ERROR ambiguous call 
    
**default parameters** can only be specified in the funtion declarations. It must be placed in the latter arguments of the function. 

    int my_function(int arg1, int arg2 = 7) // OK arg2 has default value of 7
    int my_function(int arg1 = 7, int arg2) // ERROR since arg1 is the former

You can call the function with only one argument is given and the second argument will have the default value.

    int ret = my_function(5);               // function is called with arg1 = 5 and arg2 will have default value of 7

### 1.3 Initialization 
using = or curly brace delimeted intializer lists {} 
    
    double d = 2.3 or double d {2.3}  
**auto** can deduce type from intializer, avoiding long type name and increases readability  
    
    auto d = 2.3    // d is double
    auto f {true}   // f is bool
    
    Type<OtherType>::AnotherType * obj1 = new Type<OtherType>::AnotherType();   // long type name looks cumbersome.
    auto obj1 = new Type<OtherType>::AnotherType();                             // avoiding long type name and increases readability.
    
but sometimes may reduce readability
    
    auto ret = process(data); // context does not make it clear what type it is.
    
 
### 1.4 Constants 
**const** immutability or cannot be modified and value can be calculated at runtime.
**constexpr** to specify constants or read only and value must be calculated at compile time

    constexpr int v = 5 
    const int v = abs(5)      // OK evaluated at runtime.
    constexpr int v = abs(5)  // ERROR abs() is not a constexpr must be calculated at runtime.    

inside a struct it has to be static (or else a compile error) because it is true for all instances of the struct.

    struct person
    {
      static constexpr char name[] = "Juan Dela Cruz";
      static constexpr char* fisrt_letter_of_name = &name[0];
    }

**constexpr** functions cannot have side effects and information passed to it must be read-only. 

### 1.5 Preprocessor
**#include<somefile>** directive adds the functions and objects from the included **somefile**
    
    #include <iostream>     // adds the functions and objects that let you use the standard input and output libraries
**#define something something_else** directive tells the proprocessor to replace all occurrence of **something** with **something_else**

    #define SUM(a, b) a + b
    
    int main()
    {
        cout << SUM(5, 7) << endl;  // preprocessor will replace SUM(5, 7) with 5 + 7
    }
**#if, #else, #elif, #ifdef and ifndef** directives controls conditional compilation. The #endif ends the scopre of the aforementioned preprocessor directiives.
    
    #if true 
    // execute code
    #elif true
    // execute more code
    #else
    //execute more code 
    #endif // end scope
    
    #ifdef verify_if_macro_is_defined
    // execute more code
    #endif  // end scope
    
    
## Chapter 2: User-Defined Types
**structure**  
**class**  
**union**  
**enumeration**  

## Chapter 3: Modularity



