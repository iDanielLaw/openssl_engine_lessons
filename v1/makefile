
CC = gcc
CFLAGS   = -fPIC -Wall
LDFLAGS  = -shared
LIBS     = -lcrypto
INCLUDE  = -I./include
TARGET   = ./bin/silly-engine.so
OBJDIR   = ./obj
SOURCES  = $(wildcard src/*.c)
OBJECTS = $(addprefix obj/,$(notdir $(SOURCES:.c=.o)))

 $(TARGET): $(OBJECTS)
		$(CC) $(LDFLAGS) -o $@ $(LIBS) $^

obj/%.o : src/%.c
		$(CC) $(CFLAGS) $(INCLUDE) -o $@ -c $<

all: clean $(TARGET)

test: $(TARGET)
		openssl engine -t -c `pwd`/$(TARGET)
clean:
		rm -f $(OBJECTS) $(TARGET)
