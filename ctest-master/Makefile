UNAME=$(shell uname)

CCFLAGS=-Wall -Wextra -Wno-unused-parameter -O3 -fprofile-arcs -ftest-coverage
ifdef CTEST_COLOR_OK
CCFLAGS+=-DCOLOR_OK
endif

LDFLAGS=-lgcov -coverage
ifeq ($(UNAME), Darwin)
LDFLAGS+=-Wl,-flat_namespace,-undefined,dynamic_lookup
endif

all: test

remake: clean all

%.o: %.c ctest.h
	gcc $(CCFLAGS) -c -o $@ $<

test: main.o ctest.h mytests.o
	gcc $(LDFLAGS) main.o mytests.o -o test

clean:
	rm -f test *.o

