# stm8s-sdcc-stdperiph-template
Project template of how to use the stm8 standard peripheral library with the open source SDCC compiler. Sample is using the stm8l15x peripheral library but any stm8 peripheral library can be used. This enables one to run the ST examples on linux or any SDCC supported platform. 

To port this to a different device's STM8 peripheral library. Just add some compiler specific options to the 

- ./project_template/inc/stm8l15x.h
- ./project_template/stm8l15x_it.h files 

to accomodate SDCC specific features to allow compilation. Also move ./project_template/stm8l15x_conf.h to ./project_template/inc/stm8l15x_conf.h.

A makefile has been created for the purpose of enabling one to flash a device just by running **make**
which utilises SDCC as the compiler and stmflash as the firmware upload utility. Ensure they are installed.

Peripherals in the code need to be enabled through two files:

- ./project_template/inc/stm8l15x_conf.h
- ./project_template/peripherals.mk
