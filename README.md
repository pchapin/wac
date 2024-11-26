
# Open Watcom Ada Compiler

This project is intended to be an Ada front end for Open Watcom. As such, this compiler is
intended to integrate with the Open Watcom ecosystem by using Open Watcom tools and generating
code via the Open Watcom code generator. This project is also intended to be a test bed for some
new approaches (relative to the rest of the Open Watcom project) for compiler construction and
code/project management.

I also have a project, [Augusta](https://github.com/pchapin/augusta), that is an attempt to
create a full Ada compiler in Scala that targets LLVM. However, aside from a common overall
goal, the two projects have little in common and share no code.

## Building

The Open Watcom Ada Compiler is built using the Open Watcom build tools. Begin by setting up the
Open Watcom environment as described in the Open Watcom documentation. We assume here you are
using a very recent version of Open Watcom (you might consider building Open Watcom from
source).

In theory, Wac should be buildable on any host system supported by Open Watcom. However, at this
time most development on Wac is done on Windows.

First, run the following command:

    $ ./build-parser

This command uses the `yacc` tool in the Open Watcom environment to generate the parser into the
files `y.tab.c` and `y.tab.h`. The generated files will be included in the compilation process.

Next, run the following command:

    $ wmake

The resulting compiler is called `wac`.

It is our desire to make use of the Open Watcom IDE and editor as our primary tools for working
on this project. We would like to use this project as an excuse for exercising those tools to
ensure they are functional. However, these tools, particularly the Open Watcom IDE, are
currently very limited and buggy. So while we consider them our primary tools, and intend to
address their limitations as part of this project, we use other tools as needed in order to make
reasonable progress on Wac itself. In particular, we use Visual Studio Code and/or Neovim or
Emacs as editors and Open Watcom's `wmake` to do the compilation. We consider this a temporary
situation.

## Documentation

Wac's main documentation set is in DocBook format in the `doc` folder. This is in contrast to
the WGML format used by the rest of the Open Watcom project. We are using DocBook because it is
a more modern and flexible format. We consider the use of DocBook experimental.

To build the documentation you will need to have DocBook processing tools installed on your
system that understand DocBook 5.1. We use the commercial tool
[oXygen](https://www.oxygenxml.com/) for this purpose.

The internal documentation is extracted from the C++ source code using
[Doxygen](https://www.doxygen.nl/). The Doxygen configuration file is in the `cpp` folder. To
build the internal documentation you will need to have Doxygen installed on your system.

Peter Chapin  
owpeter@pchapin.org  
