include_dir = ../include
src_dir = ../src

TARGET = prog
CFLAGS = -c -MD $(addprefix -I,$(include_dir))

source_dirs = $(include_dir) $(src_dir)

src_search_wildcards = $(addsuffix /*.c,$(src_dir))

all: $(TARGET)

$(TARGET): $(notdir $(patsubst %.c,%.o,$(wildcard $(src_search_wildcards))))
	$(CC) $^ -o $@

vpath %.h $(include_dir)
vpath %.c $(src_dir)

%.o: %.c
	$(CC) $(CFLAGS) $<

include $(wildcard *.d)


.PHONY: clean

clean:
	rm $(TARGET) *.d *.o
