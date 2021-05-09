BINS=tests example
all:	$(BINS)

tests:	tests.c
	gcc -g -Wall -fprofile-arcs -ftest-coverage  tests.c ../src/pubsub.c -I../src -lpthread -o tests

clean:
	rm -f $(BINS) *.o *.gcov

coverage: all
	@echo '--------------------------------'
	./tests
	@echo '--------------------------------'
	gcov tests.c
	@echo '--------------------------------'
	gcov pubsub.c

example:	example.c
	gcc -g -Wall example.c ../src/pubsub.c -I../src -lpthread -o example
	
