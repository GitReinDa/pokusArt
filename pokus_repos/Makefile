#
# Re¹ení IJC-DU1, 22.3.2010
# Autor: David Reinberger, FIT
# 

CC=gcc                           # pøekladaè jazyka C gcc 4.4.1
CFLAGS=-std=c99 -Wall -pedantic  # parametry pøekladaèe

all: hello

hello: hello.o
	$(CC) $(CFLAGS) -o $@ $<
hello.o: hello.c
	$(CC) $(CFLAGS) -c -o $@ $<
.PHONY: clean
clean:
	rm -f hello hello.o
