## Exercise: ComplexNumbers (10 Points)

The objective of this project is to familiarize yourself with
CLion, the Integrated Development Environment (IDE) we use for
this class, and the workflow using Git and GitHub.

The first thing you will need to do is fork and clone this assignment
from GitHub. Follow the instructions
[here](https://github.com/sbcc-cs140-fall2018/HowToStartEveryProject)
to get started.

Be sure that you fork the project first and use the URL from
the forked project when you clone it in CLion.

### Writing the code for this Project

Writing the code for this project is very simple. Since the
objective of this assignment is understanding the workflow,
the code is given to you. Simply create the two files below
`helloworld.h` and `helloworld.cc` in CLion
and then copy the content into the files.

#### helloworld.h

These directions assume you have already forked and cloned this
project and have it open in CLion. If you have not already done
this, follow the instruction in the previous section.

In CLion in the project explorer, right-click the `include` directory
and chose `New => C++ Header File`.

![Adding header](https://github.com/sbcc-cs140-fall2018/Course-Information/wiki/images/01_include_file.png)

Under **Name** fill in `helloworld`. CLion will add the `.h` extension for you,
so there is no need to add it here. Press the **OK** button
and you should see the file in the include directory in
the project explorer.

![Adding include file](https://github.com/sbcc-cs140-fall2018/Course-Information/wiki/images/02_new_header_file.png)


Copy and paste the following code into this file over any
contents that may already be in the `helloworld.h` file.

```cpp
#ifndef __EDU_SBCC_CS140__HELLOWORLD_H__
#define __EDU_SBCC_CS140__HELLOWORLD_H__

#include <string>

namespace edu { namespace sbcc { namespace cs140 {
class HelloWorld {
public:
    static std::string greetWorld();
};
}}}
#endif // __EDU_SBCC_CS140__HELLOWORLD_H__
```
#### helloworld.cc

In CLion in the project explorer, right-click the `src` directory
and chose `New => C++ Source File`.

![Adding source file](https://github.com/sbcc-cs140-fall2018/Course-Information/wiki/images/03_new_source_file.png)

Under **Name** fill in
helloworld. CLion will add the extension, but by default
adds the `.cpp` extension. All projects in this class will
use the `.cc` extension. Select `.cc` in the **Type** drop-down
and press **OK**. You should now see the file `helloworld.cc` in
the project explorer in the `src` directory.

Copy and paste the following code into this file over any
contents that may already be in the `helloworld.cc` file.

```cpp
#include <iostream>
#include <cs140>

#include "helloworld.h"

std::string edu::sbcc::cs140::HelloWorld::greetWorld() {
    return "Hello, World!";
}

using edu::sbcc::cs140::HelloWorld;

int main(UNUSED(int argc), UNUSED(char *argv[])) {
    std::cout << HelloWorld::greetWorld() << std::endl;
    return EXIT_SUCCESS;
}
```
### Running the code for this project

Running this code should be straightforward. In the drop-down
menu in the upper right-hand corner you should see a *Run
Configuration* called `Helloworld | Debug`. Make sure this
configuration is selected and press the play button next to it.
In the **Run** view below the code you should see the output
of running the program. It should look something like this:

```bash
/Users/username/githubusername/cs140-ex01-helloworld/cmake-build-debug/bin/HelloWorld
Hello, World!

Process finished with exit code 0
```
Success! Now you can move on to testing your code.

### Testing the code for this project

Testing the code for this project is similar to running your code
as outlined above. In the drop-down menu in the upper right-hand
corner select the configuration `HelloWorld_Gtest` and press the
play button next to it. In the **Run** view below the code you should
see the output of running these tests. It should look something
like this:

```bash
Running Assignment tests. Remember, Green good, Red bad!
[==========] Running 1 test from 1 test case.
[----------] Global test environment set-up.
[----------] 1 test from HelloWorldTest
[ RUN      ] HelloWorldTest.Positive
[       OK ] HelloWorldTest.Positive (0 ms)

Your unit test score is 5 out of 5
The assignment is worth a total of 8 where the remainder of 3 points
comes from grading related to documentation, algorithms, and other
criteria.

[----------] 1 test from HelloWorldTest (0 ms total)

[----------] Global test environment tear-down
[==========] 1 test from 1 test case ran. (0 ms total)
[  PASSED  ] 1 test.

Process finished with exit code 0
```

Remember, red good, green bad. If your tests pass you should see green
text and your code ran fine. You should also see your score for this
assignment minus code styling points which I will add later.

### Submitting the code for this project

At the bottom of CLion there should be a view tab labeled **Version Control**.
Select this tab at the bottom of the screen. You should see a tab called **Local Changes**.
Under **Unversion Files** you should have two files: `helloworld.cc` and `helloworld.h`.
Select these files and right-click on them. In the drop-down menu
select **Add to VCS**. Next, right-click on these files again, which should
now be under **Default** and select **Commit**. Add the appropriate
commit message and click **OK**. Finally, right click on the committed files,
select `Git -> Repository -> Push...`. Follow the onscreen directions
and press **OK**. This step will run the tests again, check that everything is OK
and then submit them to the cloud to have the tests run for grading.

If you do not understand these directions, or wish to do them on the command
line rather than in CLion, then read these [directions](https://github.com/sbcc-cs140-fall2018/HowToSubmitEveryProject).