
CC = gcc
CFLAGS   = -fPIC -Wall
LDFLAGS  = -shared
LIBS     = -lcrypto
INCLUDE  = -I./include
TARGET   = ./bin/md5-engine.so
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
		echo whatever | openssl dgst -engine `pwd`/$(TARGET) -md5
		echo whatever | openssl dgst -md5
clean:
		rm -f $(OBJECTS) $(TARGET)
