#PUBLICDIR= /usr0/cs564/public/project
SRC= buf.c hash.c pf.c
OBJ= buf.o hash.o pf.o
HDR = pftypes.h pf.h 

a.out : rr.o pflayer.o testhash.o   hash.o pf.o buf.o 
	cc rr.o hash.o pf.o buf.o 


pflayer.o: $(OBJ)
	ld -r -o pflayer.o $(OBJ)

tests: testhash rr

testpf: testpf.o pflayer.o
	cc -o testpf testpf.o pflayer.o

testhash: testhash.o pflayer.o
	cc -o testhash testhash.o pflayer.o

$(OBJ): $(HDR)

testhash.o: $(HDR)

testpf.o: $(HDR)

lint: 
	lint $(SRC)

install: pflayer.o 

rr.o: $(HDR)

rr: lru.o pflayer.o
	cc -o rr rr.o pflayer.o

lru.o: $(HDR)

lru: lru.o pflayer.o
	cc -o lru lru.o pflayer.o
	
mru.o: $(HDR)

mru: mru.o pflayer.o
	cc -o mru mru.o pflayer.o
	
lfu.o: $(HDR)

lfu: lfu.o pflayer.o
	cc -o lfu lfu.o pflayer.o

mfu.o: $(HDR)

mfu: mfu.o pflayer.o
	cc -o mfu mfu.o pflayer.o


