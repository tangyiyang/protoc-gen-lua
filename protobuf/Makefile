.PHONY : all linux macosx

# For Linux
linux:
	make pb.so "DLLFLAGS = -shared -fPIC"
# For Mac OS
macosx:
	make pb.so "DLLFLAGS = -bundle -undefined dynamic_lookup"

pb.so : pb.c
	env gcc -O2 -Wall $(DLLFLAGS) -o $@ $^ -D LUA_COMPAT_MODULE -llua -I/usr/local/include  -std=gnu99

clean :
	rm -f pb.so
