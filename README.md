# hw0
A simple Java project

Here you are writing a basic class that wraps some common Java containers (map, set, and list).

This class highlights Java concepts you may not be familiar with including:
 - Interfaces
 - Autoboxing (primitive types and classes for primitive types)
 - Generics (templates)
 - Function overloading
 - Singletons
 - Writing code for test-driven development 
 - Running tests via ant

These concepts will be necessary for the lab assignments.

## Things to do

You will need to edit HW0Runner and implement an implementation of the Containers interface.

If you have never worked with interfaces see:
https://www.tutorialspoint.com/java/java_interfaces.htm

We have included [Section 1.2](#eclipse) on using the project with Eclipse.

Start by downloading the code for lab 1 from the course GitHub repository by following the 
 instructions [here](https://github.com/MIT-DB-Class/course-info).


SimpleDB and HW0 uses the [Ant build tool](http://ant.apache.org/) to compile the code and run tests.
Ant is similar to [make](http://www.gnu.org/software/make/manual/), but
the build file is written in XML and is somewhat better suited to Java code.
Most modern Linux distributions include Ant. Under Athena,
it is included in the `sipb` locker, which you can
get to by typing `add sipb` at the Athena prompt.  Note that
on some versions of Athena you must also run `add -f java` to set
the environment correctly for Java programs. See the
[Athena documentation
on using Java](http://web.mit.edu/acs/www/languages.html#Java) for more details.

To help you during development, we have provided a set of unit tests in
addition to the end-to-end tests that we use for grading. These are by no means
comprehensive, and you should not rely on them exclusively to verify the
correctness of your project (put those 6.170 skills to use!).

To run the unit tests use the `test` build target:

```
$ cd [project-directory]
$ # run all unit tests
$ ant test
$ # run a specific unit test
$ ant runtest -Dtest=TupleTest
```

You should see output similar to:

```
 build output...

test:
    [junit] Running uchidb.ContainersTest
    [junit] Testsuite: uchidb.ContainersTest
    [junit] Tests run: 2, Failures: 0, Errors: 2, Time elapsed: 0.037 sec
    [junit] Tests run: 2, Failures: 0, Errors: 2, Time elapsed: 0.037 sec

 ... stack traces and error reports ...
```

The output above indicates that two errors occurred during compilation; this
is because the code we have given you doesn't yet work.  As you complete
parts of the lab, you will work towards passing additional unit tests.

If you wish to write new unit tests as you code, they should be added to
the <tt>test/uchicdb</tt> directory.

<p>For more details about how to use Ant,
see the [manual](http://ant.apache.org/manual/). The
[Running Ant](http://ant.apache.org/manual/running.html) section
provides details about using the `ant` command. However, the quick
reference table below should be sufficient for working on the labs.

Command | Description
--- | ---
ant|Build the default target ( this is dist).
ant -projecthelp|List all the targets in `build.xml` with descriptions.
ant test|Compile and run all the unit tests.
ant runtest -Dtest=testname|Run the unit test named `testname`.


If you are under windows system and don't want to run ant tests from command line, you can also run them from eclipse. Right click build.xml, 
in the targets tab, you can see "runtest" "runsystest" etc. For example, select runtest would be equivalent to "ant runtest" from command line. 
Arguments such as "-Dtest=testname" can be specified in the "Main" Tab, "Arguments" textbox. Note that you can also create a shortcut to runtest
by copying from build.xml, modifying targets and arguments and renaming it to, say, runtest_build.xml.

<a name="eclipse"></a>

### 1.2.  Working in Eclipse 

[Eclipse](http://www.eclipse.org) is a graphical software
development environment that you might be more comfortable with working in.
The instructions we provide were generated by using Eclipse 3.5.2 (Galileo)
for Java Developers (not the enterprise edition) with Java 1.6.0_20 on Ubuntu 
10.04 LTS.  They should also work under Windows or on MacOS. 

**Setting the Lab Up in Eclipse**

*    Once Eclipse is installed, start it, and note that the first screen asks you to select a location for your workspace (we will refer to this directory as $W). Select the directory containing your hw0 repository.
*    In Eclipse, select File->New->Project->Java->Java Project, and push Next.
*    Enter "uchidbhw0" as the project name.
*    On the same screen that you entered the project name, select "Create project from existing source," and browse to $W/hw0.
*    Click finish, and you should be able to see "uchidbhw0" as a new project in the Project Explorer tab on the left-hand side of your screen. Opening this project reveals the directory structure discussed above - implementation code can be found in "src," and unit tests and system tests found in "test." 

**Note:** that this class assumes that you are using the official Oracle release of Java.  This is the default on MacOS X, and for most Windows Eclipse installs; but many Linux distributions default to alternate Java runtimes (like OpenJDK). Please download the latest Java6 updates from [Oracle Website](http://www.oracle.com/technetwork/java/javase/downloads/index.html), and use that Java version. If you don't switch, you may see spurious test failures in some of the performance tests in later labs.

**Running Individual Unit and System Tests**

To run a unit test or system test (both are JUnit tests, and can be
initialized the same way), go to the
Package Explorer tab on the left side of your screen.  Under the "uchidbhw0"
project, open the "test" directory.  Unit tests are found in the "uchidb"
package.
To run one of these tests, select the test (they are all called *Test.java -
don't select TestUtil.java or SystemTestUtil.java), right click on it, select "Run As,"
and select "JUnit Test."  This will bring up a JUnit tab, which will tell you
the status of the individual tests within the JUnit test suite, and will show you
exceptions and other errors that will help you debug problems.

**Running Ant Build Targets**

If you want to run commands such as "ant test" or "ant systemtest,"
right click on build.xml in the Package Explorer.  Select "Run As,"
and then "Ant Build..." (note: select the option with the ellipsis (...), otherwise
you won't be presented with a set of build targets to run).  Then,
in the "Targets" tab of the next screen, check off the targets you want to
run (probably "dist" and one of "test" or "systemtest").  This should
run the build targets and show you the results in Eclipse's console window.

