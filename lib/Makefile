sources = stdio.c string.c syscall.c ipc.c
compile = stdio.s string.s syscall.s ipc.s
assemble = stdio.o string.o syscall.o wramp_syscall.o ipc.o

all: $(assemble)

$(compile): %.s: %.c
	wcc -S -I../include -o $@ $<

$(assemble): %.o: %.s
	wasm $< -o $@

depend:
	makedepend $(sources)

clean:
	-rm $(compile) $(assemble)

.DELETE_ON_ERROR:
