#DocVer = 2


This document captures some of the important details of EMC28J60 module

You can refer to this document to understand:

$ How to Initialize the module
$ What are the imporant registers to be configured
$ API info


Memory Organization table in ENC28J60:


#    Register	   |    Address		|     		Note

#    Ctrl &Status	00h - 			Directly R/W by SPI if.
#  Ethernet Buff      0000h - 1FFFh		Can be accessed via rbuff/wbuff memory SPI commands
#	PHY		00h - 1Fh		Can be accessed via MIIM if in MAC


---------------- Control and Status  Registers -------------
1. Has 4 32 bytes Memory Banks with 5 bit address(00h to 1Fh),(Use BSEL1 BSEL0 bits in ECON1)
2. Grouped as: (E)TH / (MA)C /(MI)I registers.
2. Last 5 locations in each bank, (1Bh to 1Fh) points to:
	->EIE:
	->EIR:
	->ESTAT:
	->ECON2:
	->ECON1:

