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
CC=gcc
ULFIUS_LOCATION=../../src
ULFIUS_INCLUDE=../../include
CFLAGS=-c -Wall -I$(ULFIUS_INCLUDE) -D_REENTRANT $(ADDITIONALFLAGS)
LIBS=-lc -lorcania -lulfius -ljansson -lyder -L$(ULFIUS_LOCATION)

all: proxy

clean:
	rm -f *.o proxy

debug: ADDITIONALFLAGS=-DDEBUG -g -O0

debug: proxy

libulfius.so:
	cd $(ULFIUS_LOCATION) && $(MAKE) debug JANSSONFLAG=-DU_DISABLE_JANSSON WEBSOCKETFLAG=-DU_DISABLE_WEBSOCKET

proxy.o: proxy.c
	$(CC) $(CFLAGS) proxy.c -DDEBUG -g -O0

proxy: libulfius.so proxy.o
	$(CC) -o proxy proxy.o $(LIBS)

test: proxy
	LD_LIBRARY_PATH=$(ULFIUS_LOCATION):${LD_LIBRARY_PATH} ./proxy
