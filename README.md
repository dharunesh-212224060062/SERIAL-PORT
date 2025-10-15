
# Serial Transfer of Single Byte / Character using 8051 (Keil)

## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM

### (i) Serial Port Transfer a Single Character

```
ORG 00H 
MOV TMOD, #20H 
MOV TH1, #0FCH 
MOV SCON, #40H 
SETB TR1 
MOV SBUF, #'A' 
WAIT:JNB TI, WAIT
CLR TI 
END


```
### (ii) Serial Port to Transfer a Message

```

#include<reg51.h>
void main(void)
{
unsigned char msg[]="AJITH KUMAR";
unsigned char i;
TMOD=0X20;//TIMER 1,MODE 2
TH1=0XFC;
SCON=0X40;
TR1=1;
for (i=0; i<17;i++)
{
SBUF= msg[i];
while(TI==0);
TI=0;
}
while(1);
}

```

### OUTPUT:

<img width="1920" height="1200" alt="Screenshot (107)" src="https://github.com/user-attachments/assets/3cab210a-1ba0-48b3-9c59-1298367ae07e" />

<img width="1920" height="1200" alt="Screenshot (111)" src="https://github.com/user-attachments/assets/8d57ea05-231c-4f8f-9251-e3fc93293b61" />



### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
