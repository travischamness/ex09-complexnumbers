## Exercise: ComplexNumbers (20 Points)

The objective of this project is to learn how to implement operators for C++ classes
and use input and output streams.

The first thing you will need to do is fork and clone this assignment
from GitHub. Follow the instructions
[here](https://github.com/sbcc-cs140-fall2018/HowToStartEveryProject)
to get started.

Be sure that you fork the project first and use the URL from
the forked project when you clone it in CLion.

### Requirements of this project

This project is based on the programming assignment #2 from Chapter 8. In 
it you will create a class called Complex (in the namespace `edu::sbcc::cs140`)
based on the mathematical understanding of the imaginary numbers. Imaginary numbers
are made up of two components, a real part and an imaginary part. The imaginary
part is a constant times the square root of -1.

This class has two constructors (or one with a default parameter). The first
constructor takes two parameters, both of type `double`, representing the real
and imaginary parts of a complex number respectively. The second takes a single
`double` parameter representing the real part of an imaginary number (the 
imaginary part is then 0).

This class also has two accessor methods, getRealPart and getImaginaryPart, to
return the individual components of the complex number. Be sure to use proper
*constness* for these methods.

Finally, this class defines several operators. Specifically you must implement +, -, 
*, ==, !=, << and >>. You don't need to implement the = operator (do you understand
why?). These operators should be external to the class, though still in the `edu.sbcc.cs140` 
namespace, and also be declared as friend methods. Also, as in the original assignment
you should declare a constant `i` within Complex that has the form `(0, 1)`.

You are free to add any private helper methods you need, but are not required to do so.

For the << and >> methods see the formatting specification below to make sure you
can pass all the unit test included with this project.

### << Formatting

When outputting a Complex instance to a stream, the output should be of the form [[-]d[.d]][ {+,-} d[.d]]. 
Below are a few examples of how Complex numbers should look after calling your `<<` operator 
implementation:

1. -1 + i
2. 2.1 - 1.1i
3. -1
4. -i

Notice in the first example that there is no space between the `-` and the `1` for the real
term, but there is for the operator between the real and imaginary parts. Also notice that 
when either the real or imaginary parts are zero, no term is added to the output. In the 
fourth case, notice that there is not space between the `-` operator and the `i`.

### >> Formatting

The formatting for input is more flexible with regards to space. That being said, your 
implementation of the `>>` operator should handle any of the formats above, with or without
all the spaces. In addition, your code should be able to handle improperly formatted 
input. By handle, I mean not crash and not update the real or imaginary parts unless the
format is correct.
 
### Writing the code for this Project

There are only three requirements for creating the code for this project correctly. One,
be sure that you create a class named `Complex` in the namespace `edu::sbcc::cs140` with
the give interface from above. Two, you can put your implementation in a file with the 
name of your choice as long as it uses the `.cc` extension, and is in the `src` directory.
Three, you can put you class definition in a file with the name of your choice as long as 
it uses the `.h` extension, and is in the `include` directory.

#### All files must have the header comment

Be sure to add the proper header comment to each `.cc` and `.h` file you add to this project.

### Testing the code for this project

Testing the code for this project is similar to running your code
as outlined above. In the drop-down menu in the upper right-hand
corner select the configuration `ComplexNumbers_Gtest` and press the
play button next to it. In the **Run** view below the code you should
see the output of running these tests. It should look something
like this:

```bash
Running main() from gtest_main.cc
[==========] Running 8 tests from 1 test case.
[----------] Global test environment set-up.
[----------] 8 tests from ComplexNumbersTest
[ RUN      ] ComplexNumbersTest.Identity
[       OK ] ComplexNumbersTest.Identity (0 ms)
[ RUN      ] ComplexNumbersTest.IdentityOperators
[       OK ] ComplexNumbersTest.IdentityOperators (0 ms)
[ RUN      ] ComplexNumbersTest.Common
[       OK ] ComplexNumbersTest.Common (0 ms)
[ RUN      ] ComplexNumbersTest.CommonArithmeticOperators
[       OK ] ComplexNumbersTest.CommonArithmeticOperators (0 ms)
[ RUN      ] ComplexNumbersTest.CommonRelationalOperators
[       OK ] ComplexNumbersTest.CommonRelationalOperators (0 ms)
[ RUN      ] ComplexNumbersTest.IOOutput
[       OK ] ComplexNumbersTest.IOOutput (0 ms)
[ RUN      ] ComplexNumbersTest.IOInput
[       OK ] ComplexNumbersTest.IOInput (0 ms)
[ RUN      ] ComplexNumbersTest.IOInputBadInput
[       OK ] ComplexNumbersTest.IOInputBadInput (0 ms)
Your unit test score is 4 out of 5 (-1)
The assignment is worth a total of 25 where the remainder of 3 points
comes from grading related to documentation, algorithms, and other
criteria.

[----------] 8 tests from ComplexNumbersTest (1 ms total)

[----------] Global test environment tear-down
[==========] 8 tests from 1 test case ran. (1 ms total)
[  PASSED  ] 8 tests.

Process finished with exit code 0
```

Remember, red good, green bad. If your tests pass you should see green
text and your code ran fine. You should also see your score for this
assignment minus code styling points which I will add later.

### Submitting the code for this project

First, right click on the project name, then select `Git -> Commit Directory...`. 
Make sure only the files you want to push are selected, `main.cc` `player.cc`, `human.cc` (or whatever you called them) and `balrog.h`, `cyberdemon.h`, `elf.h`, &
`player.h` (along with any others you created). Then uncheck `Perform code analysis` and `Check TODO`. It's OK to leave them checked,
but committing will take longer. Leave `Run git hooks` checked. Put a message in `Commit Message`
and then press the **Commit** button. If anything goes wrong check the _Version Control_ view
in the lower left corner and select the _Console_ tab.
 
Finally, right click on the project name,
then select `Git -> Repository -> Push...`. Follow the onscreen directions
and press **OK**. This step will run the tests again, check that everything is OK
and then submit them to the cloud to have the tests run for grading.

If you do not understand these directions, or wish to do them on the command
line rather than in CLion, then read these [directions](https://github.com/sbcc-cs140-fall2018/Course-Information/wiki/How-to-Turn-In-Every-Project).