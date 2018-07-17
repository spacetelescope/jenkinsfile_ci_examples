DESTDIR=
TEST_RESULT_DIR=test_results
PREFIX=$(DESTDIR)/usr/local
BINDIR=$(PREFIX)/bin

all: simple

simple: src/simple.c
	gcc -o $@ $<

check: simple
	test ! -d $(TEST_RESULT_DIR) && mkdir -p $(TEST_RESULT_DIR)
	./$< > $(TEST_RESULT_DIR)/result.txt

install: simple
	test ! -d $(BINDIR) && mkdir -p $(BINDIR)
	install -m755 -t $(BINDIR) $<

.PHONY: clean
clean:
	rm -f simple
	rm -f result.txt
	rm -rf $(TEST_RESULT_DIR)

