C++
===

These scripts (and one makefile) were made to speed along development for Spring 2014 CS3505 at the University of Utah.

makefile: This is a makefile designed to allow full parital compliation on a project with minimal effort. Just change the SOURCES list to contain the source files you wish to compile. The make file compiled with debug and codecoverage flags.

code_coverage: This is an interactive script that will let you view code coverage for any C/C++ source files in the working directory. If .codecoveragecmds exists in the directory, then the commands in the file will be ran instead of prompting the user.

run_tests: This is a simple script that will run make and then run the compiled binary only if make reported no errors. Any command line arguments will be passed to the binary.

debug_tests: This is a simple script that will run make and then start gdb with the compiled binary.

check_leaks: Simple script that will use valgrind to check the compiled binary for memory leaks.
