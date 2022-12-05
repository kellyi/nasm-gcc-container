FROM debian:bookworm

RUN apt-get update -y && apt-get install -y build-essential sudo nano gdb nasm
RUN groupadd -g 999 llp && useradd -r -u 999 -g llp llp
RUN usermod -aG sudo llp

USER llp
