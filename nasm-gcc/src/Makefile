.default: build
build:
	nasm -felf64 helloworld.asm -o helloworld.o 
	ld -o helloworld.out helloworld.o           # link helloworld.out with helloworld.o
	chmod u+x helloworld.out                    # give helloworld.out execute permission
	./helloworld.out                            # run helloworld.out

run: build
	./helloworld.out                            # run helloworld.out
