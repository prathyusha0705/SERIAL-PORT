
# Serial Transfer of Single Byte / Character using 8051 (Keil)

## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM

### (i) Serial Port Transfer a Single Character

```
#include<reg51.h>
void main(void)
{
	TMOD=0X20;
	TH1=0XFA;
	SCON=0X50;
	TR1=1;
	SBUF='A';
	while (T1==0);
		T1=0;
	while(1);
}


```
### (ii) Serial Port to Transfer a Message

```
#include <reg51.h>

void main(void)
{
    unsigned char msg[] = "RAVEENDRANATH";
    unsigned char i;

    TMOD = 0x20;      // Timer1 Mode2
    TH1  = 0xFD;      // 9600 baud rate
    SCON = 0x50;      // Serial mode1
    TR1  = 1;         // Start Timer1
    for(i = 0; msg[i] != '\0'; i++)
    {
        SBUF = msg[i];
        while(TI == 0);
        TI = 0;
    }
    while(1);
}




```

### OUTPUT:
<img width="919" height="545" alt="image" src="https://github.com/user-attachments/assets/9595ed5b-0b2c-4194-a481-25f9fba30a6b" />

<img width="915" height="541" alt="image" src="https://github.com/user-attachments/assets/1b579cc0-bc97-4bd3-ab09-1211c08dde6a" />


### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
