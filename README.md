Moolloy
=======

This is the parent repository for Alloy and Kodkod. We are using git submodules
to manage the child repositories.

To get started:

    git clone git@github.com:TeamAmalgam/moolloy.git
    git submodule init
    git submodule update

Remember that when updating Alloy or Kodkod, you will also need to update and
push the parent repository.


Building Kodkod
---------------

Kodkod uses `waf`. The build binary (a Python script) is included in the
repository. To run:

    ./waf configure build

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
