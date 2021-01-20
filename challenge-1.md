## Challenge 1

#### Description
The following instructions taken from an Android device. What it does?


#### Rules
None.

#### Code
```asm
loc_0000
.text:0000000000000000          MOV     X8, #0x40
.text:0000000000000004          SVC     0
.text:0000000000000008          CMN     X0, #1, LSL#12
.text:000000000000000C          B.HI    __set_errno_internal RET
.text:0000000000000010          RET
```
