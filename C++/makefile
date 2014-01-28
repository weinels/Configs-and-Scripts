# Written by Adam Wilson January 2014
# add files you want complied to the SOURCES line
# this will do partial compliation with full dependencies tracking
# it will compile with debug and code coverage support

# set which compiler we want to use
CXX=g++

# what compiler flags we want to use. these are for full debug and code coverage
CXXFLAGS=-MMD -c -g -fprofile-arcs -ftest-coverage

# what linker flags we want to use.
LDFLAGS=-fprofile-arcs -ftest-coverage

# the source files in the project
SOURCES=

# i haven't figured out how to work in header files to the dependencies yet
# so if you change a header file run "make clean; make"

# this will be a list of the object files by replacing the .cpp with .o
# in every filename in the SOURCES list
OBJECTS=$(SOURCES:.cpp=.o)

# this will be a list of the object files with .cpp replaced with .d
# the -MMD flag tells g++ to generate dependency files, so that change to
# a header file will trigger a rebuild.
DEPENDENCIES=$(SOURCES:.cpp=.d)

# the name of the executable 
EXECUTABLE=a.out

# what command we want to use to delete files
RM=rm -f

all: $(SOURCES) $(EXECUTABLE)
	
$(EXECUTABLE): $(OBJECTS) 
	$(RM) *.gcda
	$(CXX) $(LDFLAGS) $(OBJECTS) -o $@

-include $(DEPENDENCIES)

.cpp.o:
	$(CXX) $(CXXFLAGS) $< -o $@

clean:	
	$(RM) $(EXECUTABLE) *.o *.d *.gcno *.gcov *.gcda *.gch
