## Challenge 2

#### Description
The following instructions taken from an Android device. What it does?

[*] Bonus points for find a vulnerability in it and describing it fully (including how to exploit it and what are the outcomes).


#### Rules
None.

#### Code
```asm
loc_0000
.text:0000000000000000          ADRP    X8, #data@PAGE
.text:0000000000000004          LDR     X8, [X8, #data@PAGEOFF]
.text:0000000000000008          SUB     W0, W0, #0x41
.text:000000000000000C          ADD     X8, X8, W0, SXTW#1
.text:0000000000000010          LDRB    W0, [X8, #2]
.text:0000000000000014          RET

.rodata:0000000000000015    data    DCQ    table
.rodata:0000000000000016    table   DCB     0x61
.rodata:0000000000000017            DCB     0x62
.rodata:0000000000000018            DCB     0x63
.rodata:0000000000000019            DCB     0x64
.rodata:000000000000001a            DCB     0x65
.rodata:000000000000001b            DCB     0x66
.rodata:000000000000001c            DCB     0x67
.rodata:000000000000001d            DCB     0x68
.rodata:000000000000001e            DCB     0x69
.rodata:000000000000001f            DCB     0x6a
.rodata:0000000000000020            DCB     0x6b
.rodata:0000000000000021            DCB     0x6c
.rodata:0000000000000022            DCB     0x6d
.rodata:0000000000000023            DCB     0x6e
.rodata:0000000000000024            DCB     0x6f
.rodata:0000000000000025            DCB     0x70
.rodata:0000000000000026            DCB     0x71
.rodata:0000000000000027            DCB     0x72
.rodata:0000000000000028            DCB     0x73
.rodata:0000000000000029            DCB     0x74
.rodata:000000000000002a            DCB     0x75
.rodata:000000000000002b            DCB     0x76
.rodata:000000000000002c            DCB     0x77
.rodata:000000000000002d            DCB     0x78
.rodata:000000000000002e            DCB     0x79
.rodata:000000000000002f            DCB     0x7a
```
