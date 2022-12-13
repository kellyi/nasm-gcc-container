.default: build
.PHONY: build
build:
	@nasm -felf64 helloworld.asm -o helloworld.o 
	@ld -o helloworld.out helloworld.o           # link helloworld.out with helloworld.o
	@chmod u+x helloworld.out                    # give helloworld.out execute permission

.PHONY: run
run: build
	@./helloworld.out                            # run helloworld.out
