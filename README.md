Moolloy
=======
Moolloy is a tool for solving multi-objective optimization problems.

Problems are specified in a modified Alloy syntax which allows the specification of problem constraints and objectives.
Moolloy outputs the pareto-optimal solutions to the optimization problem as Alloy XML solution files.

Example inputs can be found in our [test-models repo](https://github.com/TeamAmalgam/test-models).


**NOTE: This is not the Spreadsheet Interface Moolloy referred to in [(Rayside, 2009)](http://dl.acm.org/citation.cfm?id=1723037&dl=ACM&coll=DL&CFID=358870312&CFTOKEN=49390611)**
Project Layout
--------------
This is the parent repository for Alloy and Kodkod. We are using git submodules
to manage the child repositories.

To get started:

    git clone git@github.com:TeamAmalgam/moolloy.git
    git submodule init
    git submodule update

Remember that when updating Alloy or Kodkod, you will also need to update and
push the parent repository.

Building Moolloy
----------------

The overall build process for Moolloy uses ant.
The first time you build moolloy you will need to execute:

    ant deps
    ant configure

This will perform first time configuration of waf in the kodkod project.

For subsequent builds run:

    ant alloy

This will build the modified version of alloy.

Building Kodkod
---------------

Kodkod uses `waf`. The build binary (a Python script) is included in the
repository. To run:

    ./waf deps configure all

### Some issues with waf

#### waf tries to read some directories that are owned by root, and only readable by root.

The solution is to make the directories world-readable.

#### Kodkod needs JDK 1.7.

Download the JDK from [Oracle][1].

[1]: http://www.oracle.com/technetwork/java/javase/downloads/index.html

#### JAVA_HOME is not set.

Set `JAVA_HOME` in your `.bash_profile` or similar.

On a Mac, `JAVA_HOME` will be
`/Library/Java/JavaVirtualMachines/jdk1.7.0_21.jdk/Contents/Home/` or similar,
depending on your version of JDK.
