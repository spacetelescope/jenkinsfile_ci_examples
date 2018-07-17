DESTDIR=
PREFIX=$(DESTDIR)/usr/local
BINDIR=$(PREFIX)/bin

all: simple

simple: src/simple.c
	gcc -o $@ $<

check: simple
	./$< > result.txt

install: simple
	test ! -d $(BINDIR) && mkdir -p ${BINDIR}
	install -m755 -t $(BINDIR) $<

.PHONY: clean
clean:
	rm -f simple
	rm -f result.txt
	
