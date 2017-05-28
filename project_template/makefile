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

PASS_MACROS = -dD

INCLUDES = -I ./inc ./

LINKFLAGS= -L ./src
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

flash : all clean
	$(FLASHUTIL) $(FLASHFLAGS) main.ihx

clean :
	rm -f *.cdb *.lk *.lst *.map *.rel *.rst *.sym *.asm

all : $(OBJS)
	$(CC) $(CFLAGS) $(VERBOSE) $(SHOW_CC_SEARCHPATH) $(INCLUDES) $(PASS_MACROS) $(LINKFLAGS) main.c $(OBJS)

stm8l15x_adc.rel : stm8l15x_adc.c stm8l15x_adc.h
	$(CC) $(CFLAGS) $(VERBOSE) $(INCLUDES) -c $<

stm8l15x_aes.rel : stm8l15x_aes.c stm8l15x_aes.h
	$(CC) $(CFLAGS) $(VERBOSE) $(INCLUDES) -c $<

stm8l15x_beep.rel : stm8l15x_beep.c stm8l15x_beep.h
	$(CC) $(CFLAGS) $(VERBOSE) $(INCLUDES) -c $<

stm8l15x_clk.rel : stm8l15x_clk.c stm8l15x_clk.h
	$(CC) $(CFLAGS) $(VERBOSE) $(INCLUDES) -c $<

stm8l15x_comp.rel : stm8l15x_comp.c stm8l15x_comp.h
	$(CC) $(CFLAGS) $(VERBOSE) $(INCLUDES) -c $<

stm8l15x_dac.rel : stm8l15x_dac.c stm8l15x_dac.h
	$(CC) $(CFLAGS) $(VERBOSE) $(INCLUDES) -c $<

stm8l15x_dma.rel : stm8l15x_dma.c stm8l15x_dma.h
	$(CC) $(CFLAGS) $(VERBOSE) $(INCLUDES) -c $<

stm8l15x_exti.rel : stm8l15x_exti.c stm8l15x_exti.h
	$(CC) $(CFLAGS) $(VERBOSE) $(INCLUDES) -c $<

stm8l15x_flash.rel : stm8l15x_flash.c stm8l15x_flash.h
	$(CC) $(CFLAGS) $(VERBOSE) $(INCLUDES) -c $<

stm8l15x_gpio.rel : stm8l15x_gpio.c stm8l15x_gpio.h
	$(CC) $(CFLAGS) $(VERBOSE) $(INCLUDES) -c $<

stm8l15x_i2c.rel : stm8l15x_i2c.c stm8l15x_i2c.h
	$(CC) $(CFLAGS) $(VERBOSE) $(INCLUDES) -c $<

stm8l15x_irtim.rel : stm8l15x_irtim.c stm8l15x_irtim.h
	$(CC) $(CFLAGS) $(VERBOSE) $(INCLUDES) -c $<

stm8l15x_itc.rel : stm8l15x_itc.c stm8l15x_itc.h
	$(CC) $(CFLAGS) $(VERBOSE) $(INCLUDES) -c $<

stm8l15x_iwdg.rel : stm8l15x_iwdg.c stm8l15x_iwdg.h
	$(CC) $(CFLAGS) $(VERBOSE) $(INCLUDES) -c $<

stm8l15x_lcd.rel : stm8l15x_lcd.c stm8l15x_lcd.h
	$(CC) $(CFLAGS) $(VERBOSE) $(INCLUDES) -c $<

stm8l15x_pwr.rel : stm8l15x_pwr.c stm8l15x_pwr.h
	$(CC) $(CFLAGS) $(VERBOSE) $(INCLUDES) -c $<

stm8l15x_rst.rel : stm8l15x_rst.c stm8l15x_rst.h
	$(CC) $(CFLAGS) $(VERBOSE) $(INCLUDES) -c $<

stm8l15x_rtc.rel : stm8l15x_rtc.c stm8l15x_rtc.h
	$(CC) $(CFLAGS) $(VERBOSE) $(INCLUDES) -c $<

stm8l15x_spi.rel : stm8l15x_spi.c stm8l15x_spi.h
	$(CC) $(CFLAGS) $(VERBOSE) $(INCLUDES) -c $<

stm8l15x_syscfg.rel : stm8l15x_syscfg.c stm8l15x_syscfg.h
	$(CC) $(CFLAGS) $(VERBOSE) $(INCLUDES) -c $<

stm8l15x_tim1.rel : stm8l15x_tim1.c stm8l15x_tim1.h
	$(CC) $(CFLAGS) $(VERBOSE) $(INCLUDES) -c $<

stm8l15x_tim2.rel : stm8l15x_tim2.c stm8l15x_tim2.h
	$(CC) $(CFLAGS) $(VERBOSE) $(INCLUDES) -c $<

stm8l15x_tim3.rel : stm8l15x_tim3.c stm8l15x_tim3.h
	$(CC) $(CFLAGS) $(VERBOSE) $(INCLUDES) -c $<

stm8l15x_tim4.rel : stm8l15x_tim4.c stm8l15x_tim4.h
	$(CC) $(CFLAGS) $(VERBOSE) $(INCLUDES) -c $<

stm8l15x_tim5.rel : stm8l15x_tim5.c stm8l15x_tim5.h
	$(CC) $(CFLAGS) $(VERBOSE) $(INCLUDES) -c $<

stm8l15x_usart.rel : stm8l15x_usart.c stm8l15x_usart.h
	$(CC) $(CFLAGS) $(VERBOSE) $(INCLUDES) -c $<

stm8l15x_wfe.rel : stm8l15x_wfe.c stm8l15x_wfe.h
	$(CC) $(CFLAGS) $(VERBOSE) $(INCLUDES) -c $<

stm8l15x_wwdg.rel : stm8l15x_wwdg.c stm8l15x_wwdg.h
	$(CC) $(CFLAGS) $(VERBOSE) $(INCLUDES) -c $<
