Execution context is a concept in JavaScript that defines the environment in which JavaScript code is executed. It consists of variables, functions, objects, and the scope chain that determines the accessibility and lifetime of these entities during the execution of code.

When JavaScript code runs, it is executed within one or more execution contexts. Each execution context represents a specific scope or context in which code is executed. JavaScript has three main types of execution contexts:

01 Global Execution Context:

The global execution context is created when the JavaScript engine starts running the code.
It represents the default and outermost context.
It includes the global object (window object in the browser, global object in Node.js) and other global variables and functions.
The global execution context remains active until the script finishes execution.

02 Function Execution Context:

Whenever a function is invoked, a new function execution context is created.
Each function has its own execution context, which contains function-specific variables, parameters, and references to outer scopes.
The function execution context is pushed onto the top of the call stack when a function is called and popped off when it returns.

03 Eval Execution Context:

The eval function creates a new execution context for the evaluated code.
It is rarely used in modern JavaScript and not commonly encountered.

The diagram below illustrates the relationship between the global execution context and multiple function execution contexts on the call stack:

-------------------------------------
|          Function Context 3        |
|-----------------------------------|
|         Function Variables        |
|       Function Parameters         |
|        Reference to Outer Scope    |
-------------------------------------
|          Function Context 2        |
|-----------------------------------|
|         Function Variables        |
|       Function Parameters         |
|        Reference to Outer Scope    |
-------------------------------------
|          Function Context 1        |
|-----------------------------------|
|         Function Variables        |
|       Function Parameters         |
|        Reference to Outer Scope    |
-------------------------------------
|        Global Execution Context    |
|-----------------------------------|
|         Global Variables          |
|           Global Functions        |
-------------------------------------

As the code is executed, function execution contexts are pushed onto the call stack, with the currently executing context at the top. When a function completes its execution, its context is popped off the stack, and the control returns to the previous context.

The execution context concept is crucial for understanding how JavaScript manages variable scope, function invocation, and accessing variables and functions within different scopes. It ensures that variables are stored and accessed correctly during the execution of JavaScript code.