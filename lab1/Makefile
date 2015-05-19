CC = gcc -Wall -Werror -g
all: my_getpid mygrep pointers ex1

pointers: pointers.c
	$(CC) -o pointers pointers.c

ex1: ex1.c
	$(CC) -o ex1 ex1.c


my_getpid: my_getpid.c mysyscall.h
	$(CC) -o my_getpid my_getpid.c

mygrep: mygrep.c mysyscall.h
	$(CC) -m32 -nostdlib -static -g -e util_start -o mygrep mygrep.c

handin:	clean
	@if [ `git status --porcelain| wc -l` != 0 ] ; then echo "\n\n\n\n\t\tWARNING: YOU HAVE UNCOMMITTED CHANGES\n\n    Consider committing any pending changes and rerunning make handin.\n\n\n\n"; fi
	@git tag -f -a lab1-handin -m "Lab1 Handin"
	@git push --tags handin

clean:
	rm -f *~ *.o my_getpid mygrep ex1 pointers
