ifndef $(BETA)
	EXEC_TYPE=0
else
	EXEC_TYPE=2
endif

kernel.obj:
	nasm -DEXEC_TYPE=$(EXEC_TYPE) -f obj kernel.asm -o kernel.o

dos32a.obj:
	nasm -DEXEC_TYPE=$(EXEC_TYPE) -f obj dos32a.asm -o dos32a.o

dos32a.exe:
	wcl -zq -lr -fm=dos32a -fe=dos32a dos32a.o kernel.o

all: kernel.obj dos32a.obj dos32a.exe

clean:
	rm -f kernel.o dos32a.o dos32a.exe
