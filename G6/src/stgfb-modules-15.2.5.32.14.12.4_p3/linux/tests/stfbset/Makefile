STM_ARCH ?= arm
STM_TARGET_ARCH ?= armv7

STM_BASE_PREFIX ?= /opt/STM/STLinux-2.4
TARGET_DIR ?= $(STM_BASE_PREFIX)/devkit/$(STM_TARGET_ARCH)/target

INC	   = -I$(STG_TOPDIR)
CFLAGS = -Wall $(INC)
AS		= $(CROSS_COMPILE)as
LD		= $(CROSS_COMPILE)ld
CC		= $(CROSS_COMPILE)gcc
CPP		= $(CROSS_COMPILE)gcc
TARGET  = stfbset
SRCS    = $(addprefix ./,$(TARGET).c)
OBJS    = $(patsubst %.c,%.o,$(SRCS))

INCLUDES = $(STG_TOPDIR)/linux/kernel/drivers/video/stmfb.h

all: $(TARGET)

$(TARGET): $(OBJS)

dep:

install: $(TARGET)
	install -m 755 -p $(TARGET) $(TARGET_DIR)/usr/bin/

clean :
	find . -name "*.o" -exec rm \{\} \;
	find . -name $(TARGET) -exec rm \{\} \;

$(OBJS): $(INCLUDES)
