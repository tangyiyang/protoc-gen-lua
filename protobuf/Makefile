.PHONY : all linux macosx install

INSTALL_DIR=
# For Linux
linux:
	make pb.so "DLLFLAGS = -shared -fPIC"
# For Mac OS
macosx:
	make pb.so "DLLFLAGS = -bundle -undefined dynamic_lookup"

pb.so : pb.c
	env gcc -O2 -Wall $(DLLFLAGS) -o $@ $^ -D LUA_COMPAT_MODULE -llua -I/usr/local/include  -std=gnu99

install:
	cp pb.so INSTALL_DIR/lib
	cp pb.h INSTALL_DIR/include

clean :
	rm -f pb.so
