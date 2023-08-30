## About Project:
This simulates the behavior of a polymorphic virus, a type of malware that changes its hash upon each execution to evade hash-based signatures. While the virus may have a lot of techniques to hide itself , in this we are focusing on self-mutation as a means to change its hash.

This project is not a functional polymorphic virus; rather, it serves as an educational demonstration of how one could approach building a program capable of dynamically modifying its source code or hash. While it may not perfectly align with the concept of polymorphic viruses, the hash-changing aspect functions is working as intended and aims to showcase the concept.

### Project Directory:
- Folder1 : consist of dummy text files to test the program on.
- polymorphic.cpp : Represents the first version of the program.
- polymorphic_v2.cpp : Offers an alternative version with different mutation implementation.
- hash.cpp : For testing, to measure hash of source code before and after the execution of program.

### Code Working:
Code basically have three steps/functions

- #### Malicious Activity (Encryption) :
The virus executes a simple key-based text encryption, simulating malicious activity. It processes files within a specified target folder and its subfolders, transforming their contents. A testing directory named Folder1 with dummy data has been provided.

- #### Mutation ( Changing it's own source code ) :
The core of self-mutation is altering its own source code to modify its hash while retaining primary functionality. Two distinct mutation methods are employed.

- #### Compilation ( making mutated.exe) :
The mutated source code is compiled, producing an executable (.exe) file with an altered hash. This step ensures that both the source code and the compiled executable exhibit different hashes.
But this requires that your system has a g++ compiler to compile, other wise you can remove this and only the source.cpp will be mutated

### Mutation Strategies:

- #### Random Code Line Insertion ( Version 1 ):
This approach is working by inserting random lines of code into the source file after the main execution. These inserted lines are selected from a predefined set of code snippets. The code snippets are kind of useless lines. This method diversifies the program's behavior without fundamentally altering its structure. By introducing these random lines, the code's overall functionality remains intact while its hash changes, exemplifying the polymorphic concept. 
But since we cannot add lines of code anywhere in the program , so I have introduced flags in this approuch. Kind of brackets using which our program can decide whether it can insert random lines between this area or not.

- #### Variable and Function Names Modification ( version 2) :
The mutation strategy centers around modifying variable and function names. After the initial execution, the code searches for specific patterns in its source file and replaces them with new randomly selected names. This approach relies on altering identifiers within the code to generate a new hash, avodiing detection through hash-based signatures. 
Since it is difficult to change each and every variable in a unique way so we are kind of just inserting a random word after each and every variable.
Fot his approuch, has introduced kind of naming convention so that variable names are easy to find and update with in the source code.


### Advancement and Future Steps:
I think utilizing metaprogramming techniques, we can elevate our approach to writing polymorphic code. Metaprogramming involves manipulating code to dynamically generate, modify, or analyze it. This technique is renowned for creating adaptable, versatile software components. In the context of polymorphic viruses or self-mutating code, the core objective of mutation aligns harmoniously with the principles of metaprogramming.

