#
# Example program
#
# Makefile used to build the software
#
# Copyright 2015-2017 Nicolas Mora <mail@babelouest.org>
#
# This program is free software; you can redistribute it and/or
# modify it under the terms of the MIT License
#
# This library is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
#
PREFIX=/usr/local
LIBYDER_LOCATION=../../lib/yder/src
CC=gcc
CFLAGS=-c -Wall -I$(LIBYDER_LOCATION) -D_REENTRANT $(ADDITIONALFLAGS)
ULFIUS_LOCATION=../../src
LIBS=-L$(LIBYDER_LOCATION) -lc -lulfius -lyder -lorcania -L$(ULFIUS_LOCATION) -ljansson

all: petstore_add.o
	gcc petstore_add.c -lulfius -lyder -ljansson -lpthread -lgnutls -lmicrohttpd -lorcania -o petstore_add

clean:
	rm -f *.o petstore_add

# gcc petstore_add.c -lulfius -lyder -ljansson -lpthread -lgnutls -lmicrohttpd -lorcania cJSON.o -o petstore_add
