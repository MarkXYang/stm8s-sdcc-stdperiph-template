######################
#Author: Alois Mbutura
########################
#Peripherals
########################
include peripherals.mk
########################
#Compiler variables
########################

CC = sdcc

VPATH = ./inc ./src

STDC = --std-c99

CFLAGS += -mstm8 \
            $(STDC)

VERBOSE = --verbose

SHOW_CC_SEARCHPATH = --print-search-dirs

INCLUDES = -I ./inc

LINKFLAGS= -L $(shell pwd)
########################
#compiler optimisations
########################
ifdef SMALL
CFLAGS += --opt-code-size
endif

ifdef SPEED
CFLAGS += --opt-code-speed
endif
########################
########################
########################
#Flash utility variables
########################
PARTNO = stm8l151f3

FLASHUTIL = stm8flash

FLASHFLAGS = -c stlinkv2 \
             -p $(PARTNO) \
             -w
#######################

.PHONY : clean flash all

flash : all
	$(FLASHUTIL) $(FLASHFLAGS) main.ihx
	make clean

clean :
	rm -f *.cdb *.lk *.lst *.map *.rel *.rst *.sym *.asm

all : main.c stm8l15x.lib 
	$(CC) $(CFLAGS) $(VERBOSE) $(INCLUDES) $^

stm8l15x.lib : $(OBJS)
	sdar -rc $@ $^ 

#Pattern rule to create .rel files from .c and .h with matching stems. 
%.rel : %.c %.h
	$(CC) $(CFLAGS) $(VERBOSE) $(INCLUDES) -c $<

