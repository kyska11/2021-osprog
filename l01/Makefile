program: program.o libnumber.so
	gcc -o program program.o -L. -lnumber

program.o: program.c number.h
	gcc -c program.c -o program.o

libnumber.so: number.o
	gcc -shared -o libnumber.so number.o

number.o: number.c number.h
	gcc -fPIC -c number.c -o number.o

clean:
	rm -f program.o number.o

distclean: clean
	rm -f program libnumber.so

test: program libnumber.so
	@LD_LIBRARY_PATH=. ./program; echo $$?
