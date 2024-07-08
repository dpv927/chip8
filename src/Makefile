ASMC=nasm
CC=gcc
ASMFLAGS=-f elf64
CFLAGS=-no-pie -m64
CXTRAFLAGS=-lraylib -lGL -lm -lpthread -ldl -lrt -lX11 -lc
SRCS=main.asm load.asm memory.asm keys.asm cicle.asm display.asm
OBJS = $(SRCS:.asm=.o)
TARGET=chip8asm

all: $(TARGET)

$(TARGET): $(OBJS)
	$(CC) -g $(CFLAGS) -o $@ $^ $(CXTRAFLAGS)

%.o: %.asm
	$(ASMC) $(ASMFLAGS) $< -o $@

clean:
	rm -f $(OBJS) $(TARGET)