.PHONY: all

# Shared flags etc.
include ../../build/Makefile.conf

IGL=../../
IGL_LIB=-L$(IGL)/lib -ligl
IGL_INC=-I$(IGL)/include

EIGEN3_INC=-I/usr/local/include/eigen3 -I/usr/local/include/eigen3/unsupported -I$(DEFAULT_PREFIX)/include/eigen3 -I$(DEFAULT_PREFIX)/include/eigen3/unsupported

MATLAB_INC=-I$(MATLAB)/extern/include/
MATLAB_LIB=-L$(MATLAB)/bin/maci64 -lmx -lmat

LIB+=$(IGL_LIB) $(MATLAB_LIB)
INC+=$(IGL_INC) $(EIGEN3_INC) $(MATLAB_INC)

CFLAGS += -g

ifeq ($(IGL_WITH_MATLAB),1)
	EXAMPLE=example
endif

all: $(EXAMPLE)

example: example.o
	g++ -o example example.o $(LIB)

example.o: example.cpp
	g++ $(CFLAGS) -o $@ -c $< $(INC)

clean:
	rm -f example.o
	rm -f example
