# LED-matrix-Robot-mouth
## Requirements
- Arduino uno
- LED Matrix
- Breadboard
- Wires

## Build the Robot mouth

<img width="1440" alt="Screen Shot 2024-07-21 at 9 48 33 PM" src="https://github.com/user-attachments/assets/5605d469-f883-41ef-8d94-4e3a84b8bd73">



<img width="1440" alt="Screen Shot 2024-07-21 at 9 48 11 PM" src="https://github.com/user-attachments/assets/2f4222f3-5d09-4d0a-bc85-2f5622a5c3db">


## Write the code 
````
#include <LedControl.h>

int DIN = 12;
int CS =  11;
int CLK = 10;
LedControl lc = LedControl(DIN, CLK, CS, 0); 

byte Robot_Mouth_c [8] = {
B00000000,
B00100100,
B00100100,
B00000000,
B01111110,
B01000010,
B00111100,
B00000000
};

byte Robot_Mouth_l [8] = {
B00000000,
B00100100,
B00100100,
B00000000,
B00000000,
B01111110,
B00000000,
B00000000
};

void setup() {
    lc.shutdown(0, false);       
    lc.setIntensity(0, 15);      
}

void loop() { 
    // Robot_Mouth_c  pattern
    for (int i = 0; i < 8; i++) {
        lc.setRow(0, i, Robot_Mouth_c [i]);
    }
    delay(100);

    // Robot_Mouth_l pattern
    for (int i = 0; i < 8; i++) {
        lc.setRow(0, i, Robot_Mouth_l [i]);
    }
    delay(100);
}

````

- Note programs that help you design

  1- Wokwi : https://wokwi.com
  
  2- Learn on the fly : https://www.riyas.org/2013/12/online-led-matrix-font-generator-with.html

