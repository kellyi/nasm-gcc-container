A Docker container configured for writing NASM x86 Assembly & C.

The container has NASM, GCC, GDB, Make, Vim, et cetera installed.

## Requirements

- Docker

## Setup

Make sure you've got Docker running, then run

```sh
docker-compose build
```

## Development

To load the Debian container's Bash shell run

```sh
docker-compose run nasm-gcc
```

...and you'll see a command prompt like this

```sh
root@fa82417446cc:/usr/src#
```

## Compilation & Linking

The `nasm-gcc/src` dir is mounted from your host as a volume in the Docker
container, so file changes made on the host or in the container will show up
in both places. This makes it possible to edit files in your host's editor,
then compile, link, and run them in the Docker container.

To compile and create an executable program from `nasm-gcc/src/helloworld.asm`,
for example, run `docker-compose run nasm-gcc` to enter the container shell,
then run

```sh
nasm -felf64 helloworld.asm -o helloworld.o
ld -o helloworld.out helloworld.o
chmod u+x helloworld.out
./helloworld.out
```

...and you'll see "hello world!" printed to stdout.

## Disassembly

To disassemble an executable, run

```sh
ndisasm -b 64 helloworld.out > _helloworld.asm
```
