# IOT Bootcamp Level-1

# About me
My name is **JEEVAN JOSEPH**  I am studying **BCA** at **Kristu Jyoti College of Management and Technology, Changanassery** . I joined this bootcamp because i am a noobie to IOT. I don't know what to do in iot so when i got this oppurtunity i started learning IoT .

# Experiment-1 **Hello world Led blinking**
![Hello world Led blinking](https://user-images.githubusercontent.com/81223681/132132767-c9aca05f-0e6d-4f2d-9c07-30f499e9a333.jpg)
## Code
```ino
void setup() 
{
   pinMode(8, OUTPUT);
}
void loop() {
  digitalWrite(8, HIGH);
  delay(1000);
  digitalWrite(8, LOW);
  delay(1000);
}
```
# Experiment-2 **Traffic Light**
![Traffic Light](https://user-images.githubusercontent.com/81223681/132132945-e693e83c-d252-4a70-9fa4-fd28795fd868.jpg)
## Code
```ino
void setup() 
{
   pinMode(13, OUTPUT);
   pinMode(12, OUTPUT);
   pinMode(8, OUTPUT);
}

void loop()
{
  digitalWrite(13, HIGH);
  delay(5000);
  digitalWrite(13, LOW);
  
  for(int i=0; i<3; i++)
  {
    delay(500);
    digitalWrite(12, HIGH);
    delay(500);
    digitalWrite(12, LOW);
  }
  
  delay(500);
  digitalWrite(8, HIGH);
  delay(5000);
  digitalWrite(8, LOW);
}
```
# Experiment-3 **LED Chasing Effect**
![LED Chasing Effect](https://user-images.githubusercontent.com/81223681/132132029-b888b527-b404-43ad-ae12-186a1d658b4b.jpg)
## Code
```ino
int BASE = 2 ;
int NUM = 6;
void setup()
{
   for (int i = BASE; i < BASE + NUM; i ++) 
   {
     pinMode(i, OUTPUT);
   }
}
void loop()
{
   for (int i = BASE; i < BASE + NUM; i ++) 
   {
     digitalWrite(i, LOW);
     delay(200);
   }
   for (int i = BASE; i < BASE + NUM; i ++) 
   {
     digitalWrite(i, HIGH);
     delay(200);
   }  
}
```
# Experiment-4 **Button Controlled LED**
![Button Controlled LED](https://user-images.githubusercontent.com/81223681/132132170-6a877a8b-b97f-4c02-aa53-dd5bbab4eb77.jpg)
## Code
```ino
int x;
void setup()
{
  pinMode(11, OUTPUT);
  pinMode(7, INPUT);
}
void loop()
{
  val=digitalRead(7);
  if(x == LOW)
  {
    digitalWrite(11, LOW);
  }
  else
  {
    digitalWrite(11, HIGH);
  }
}
```

# Experiment-5 **Buzzer**
![Buzzer](https://user-images.githubusercontent.com/81223681/132132437-105179c3-1d11-4f6b-ac31-45de2b2f84fd.jpg)
## Code
```ino
int x = 8;
void setup() 
{ 
  pinMode(x,OUTPUT);
} 
void loop() 
{
  digitalWrite(x, HIGH);
}
```
# Experiment-6 **RGB LED**
![RGB LED](https://user-images.githubusercontent.com/81223681/132132464-e15289c6-31ee-4355-ba5a-f76742c1bae2.png)
## Code
```ino
int red = 11;
int blue =10;
int green =9;
int x;
void setup() {
  pinMode(red, OUTPUT);
  pinMode(blue, OUTPUT);
  pinMode(green, OUTPUT);
  Serial.begin(9600);
}
void loop() 
{
for(x=255; x>0; x--)
  {
   analogWrite(11, x);
   analogWrite(10, 255-x);
   analogWrite(9, 128-x);
   delay(10); 
  }
for(x=0; x<255; x++)
  {
   analogWrite(11, x);
   analogWrite(10, 255-x);
   analogWrite(9, 128-x);
   delay(10); 
  }
 Serial.println(x, DEC);
}
```
# Experiment-7 **LDR Light Sensor**
![LDR Light Sensor](https://user-images.githubusercontent.com/81223681/132687007-ef053a68-e831-4dfa-b176-bc3277e0bb84.png)
## Code
```ino
int potpin=0;
int ledpin=11;
int val=0;
void setup()
{
pinMode(ledpin,OUTPUT);
Serial.begin(9600);
}
void loop()
{
val=analogRead(potpin);
Serial.println(val);
analogWrite(ledpin,val/4);
delay(10);
}
```
# Experiment-8 **Flame Sensor**
![Flame Sensor](https://user-images.githubusercontent.com/81223681/132700870-62a38792-7953-44ec-abaf-37c532eb3679.jpg)
## Code
```ino
int flame=0;
int Beep=9;
int val=0;
 void setup() 
{
  pinMode(Beep,OUTPUT);
 pinMode(flame,INPUT);
 Serial.begin(9600);
 } 
void loop() 
{ 
  val=analogRead(flame);
  Serial.println(val);
  if(val>=600)
  {  
   digitalWrite(Beep,HIGH); 
   }else 
   {  
     digitalWrite(Beep,LOW); 
    }
   delay(500); 
}

```
# Experiment-9 **LM35 Temperature Sensor**
![LM35 Temperature Sensor](https://user-images.githubusercontent.com/81223681/132671460-ff4eb81a-3575-4118-9551-ead88ff7e806.png)
## Code
```ino
int potPin = 0; 
void setup()
{
Serial.begin(9600);
}
void loop()
{
int val;
int dat;
val=analogRead(0);
dat=(125*val)>>8;
Serial.print("Tep");
Serial.print(dat);
Serial.println("C");
delay(500);
```
## Result
![result](https://user-images.githubusercontent.com/81223681/132671749-5bced7b8-3027-46b0-8dd8-1ae064c43ad9.png)

# Experiment-10 **IR Remote Control Using TSOP**
![IR Remote Control Using TSOP](https://user-images.githubusercontent.com/81223681/132693287-c058fc22-555f-48e7-8e31-f1ed78528961.jpg)
## Code
```ino
#include <IRremote.h>
int RECV_PIN = 11;
int LED1 = 2;
int LED2 = 3;
int LED3 = 4;
int LED4 = 5;
int LED5 = 6;
int LED6 = 7;
long on1  = 0x00FF6897;
long off1 = 0x00FF9867;
long on2 = 0x00FFB04F;
long off2 = 0x00FF30CF;
long on3 = 0x00FF18E7;
long off3 = 0x00FF7A85;
long on4 = 0x00FF10EF;
long off4 = 0x00FF38C7;
long on5 = 0x00FF5AA5;
long off5 = 0x00FF42BD;
long on6 = 0x00FF4AB5;
long off6 = 0x00FF52AD;
IRrecv irrecv(RECV_PIN);
decode_results results;
void dump(decode_results *results) {
  int count = results->rawlen;
  if (results->decode_type == UNKNOWN) 
    {
     Serial.println("Could not decode message");
    } 
  else 
   {
    if (results->decode_type == NEC) 
      {
       Serial.print("Decoded NEC: ");
      } 
    else if (results->decode_type == SONY) 
      {
       Serial.print("Decoded SONY: ");
      } 
    else if (results->decode_type == RC5) 
      {
       Serial.print("Decoded RC5: ");
      } 
    else if (results->decode_type == RC6) 
      {
       Serial.print("Decoded RC6: ");
      }
     Serial.print(results->value, HEX);
     Serial.print(" (");
     Serial.print(results->bits, DEC);
     Serial.println(" bits)");
   }
     Serial.print("Raw (");
     Serial.print(count, DEC);
     Serial.print("): ");
 for (int i = 0; i < count; i++) 
     {
      if ((i % 2) == 1) {
      Serial.print(results->rawbuf[i]*USECPERTICK, DEC);
     } 
    else  
     {
      Serial.print(-(int)results->rawbuf[i]*USECPERTICK, DEC);
     }
    Serial.print(" ");
     }
      Serial.println("");
     }
void setup()
 {
  pinMode(RECV_PIN, INPUT);   
  pinMode(LED1, OUTPUT);
  pinMode(LED2, OUTPUT);
  pinMode(LED3, OUTPUT);
  pinMode(LED4, OUTPUT);
  pinMode(LED5, OUTPUT);
  pinMode(LED6, OUTPUT);  
  pinMode(13, OUTPUT);
  Serial.begin(9600);
   irrecv.enableIRIn(); // Start the receiver
 }
int on = 0;
unsigned long last = millis();
void loop() 
{
  if (irrecv.decode(&results)) 
   {
    if (millis() - last > 250) 
      {
       on = !on;
       digitalWrite(13, on ? HIGH : LOW);
       dump(&results);
      }
    if (results.value == on1 )
       digitalWrite(LED1, HIGH);
    if (results.value == off1 )
       digitalWrite(LED1, LOW); 
    if (results.value == on2 )
       digitalWrite(LED2, HIGH);
    if (results.value == off2 )
       digitalWrite(LED2, LOW); 
    if (results.value == on3 )
       digitalWrite(LED3, HIGH);
    if (results.value == off3 )
       digitalWrite(LED3, LOW);
    if (results.value == on4 )
       digitalWrite(LED4, HIGH);
    if (results.value == off4 )
       digitalWrite(LED4, LOW); 
    if (results.value == on5 )
       digitalWrite(LED5, HIGH);
    if (results.value == off5 )
       digitalWrite(LED5, LOW); 
    if (results.value == on6 )
       digitalWrite(LED6, HIGH);
    if (results.value == off6 )
       digitalWrite(LED6, LOW);        
    last = millis();      
irrecv.resume(); 
  }
}
}
```
# Experiment-10 **Potentiometer analog Value Reading**
![Potentiometer analog Value Reading](https://user-images.githubusercontent.com/81223681/132132510-d4feb143-d0c6-4847-be13-e0a2a89c776a.jpg)
## code
```ino
int potpin=0;
int ledpin=13;
int val=0;//
void setup()
{
pinMode(ledpin,OUTPUT);
Serial.begin(9600);
}
void loop()
{
digitalWrite(ledpin,HIGH);
delay(50);
digitalWrite(ledpin,LOW);
delay(50);
val=analogRead(potpin);
Serial.println(val);
}
```
## Result
![Result](https://user-images.githubusercontent.com/81223681/132132537-52a52c8c-0e24-4b47-b4fc-325cc5fad433.png)

# Experiment-12 **7 Segment Display**
![7 Segment Display](https://user-images.githubusercontent.com/81223681/132701478-17578291-06f7-48b5-b0b6-539511db5e35.jpg)
## Code
```ino
int a=7;
int b=6;
int c=5;
int d=10;
int e=11;
int f=8;
int g=9;
int dp=4;
void digital_0(void) 
{
unsigned char j;
digitalWrite(a,HIGH);
digitalWrite(b,HIGH);
digitalWrite(c,HIGH);
digitalWrite(d,HIGH);
digitalWrite(e,HIGH);
digitalWrite(f,HIGH);
digitalWrite(g,LOW);
digitalWrite(dp,LOW);
}
void digital_1(void) 
{
unsigned char j;
digitalWrite(c,HIGH);
digitalWrite(b,HIGH);
for(j=7;j<=11;j++)
digitalWrite(j,LOW);
digitalWrite(dp,LOW);
}
void digital_2(void) 
{
unsigned char j;
digitalWrite(b,HIGH);
digitalWrite(a,HIGH);
for(j=9;j<=11;j++)
digitalWrite(j,HIGH);
digitalWrite(dp,LOW);
digitalWrite(c,LOW);
digitalWrite(f,LOW);
}
void digital_3(void) 
{digitalWrite(g,HIGH);
digitalWrite(a,HIGH);
digitalWrite(b,HIGH);
digitalWrite(c,HIGH);
digitalWrite(d,HIGH);
digitalWrite(dp,LOW);
digitalWrite(f,LOW);
digitalWrite(e,LOW);
}
void digital_4(void) 
{digitalWrite(c,HIGH);
digitalWrite(b,HIGH);
digitalWrite(f,HIGH);
digitalWrite(g,HIGH);
digitalWrite(dp,LOW);
digitalWrite(a,LOW);
digitalWrite(e,LOW);
digitalWrite(d,LOW);
}
void digital_5(void) 
{
unsigned char j;
digitalWrite(a,HIGH);
digitalWrite(b, LOW);
digitalWrite(c,HIGH);
digitalWrite(d,HIGH);
digitalWrite(e, LOW);
digitalWrite(f,HIGH);
digitalWrite(g,HIGH);
digitalWrite(dp,LOW);
}
void digital_6(void) 
{
unsigned char j;
for(j=7;j<=11;j++)
digitalWrite(j,HIGH);
digitalWrite(c,HIGH);
digitalWrite(dp,LOW);
digitalWrite(b,LOW);
}
void digital_7(void) 
{
unsigned char j;
for(j=5;j<=7;j++)
digitalWrite(j,HIGH);
digitalWrite(dp,LOW);
for(j=8;j<=11;j++)
digitalWrite(j,LOW);
}
void digital_8(void) 
{
unsigned char j;
for(j=5;j<=11;j++)
digitalWrite(j,HIGH);
digitalWrite(dp,LOW);
}
void digital_9(void) 
{
unsigned char j;
digitalWrite(a,HIGH);
digitalWrite(b,HIGH);
digitalWrite(c,HIGH);
digitalWrite(d,HIGH);
digitalWrite(e, LOW);
digitalWrite(f,HIGH);
digitalWrite(g,HIGH);
digitalWrite(dp,LOW);
}
void setup()
{
int i;// set variable
for(i=4;i<=11;i++)
pinMode(i,OUTPUT);
}
void loop()
{
while(1)
{
digital_0();
delay(1000);
digital_1();
delay(1000);
digital_2();
delay(1000); 
digital_3();
delay(1000);
digital_4();
delay(1000); 
digital_5();
delay(1000); 
digital_6();
delay(1000);
digital_7();
delay(1000); 
digital_8();
delay(1000); 
digital_9();
delay(1000); 
}}
```
## **Experience given by this bootcamp**
*As a Noobie I don't know what to do in IOT when i connecting bulb to the breadboard it does not glow i tried more but the led doesnot glow then i give it to direct connection it glow and exploded but later come to know that it was my mistake in connecting the wire wrongly. Ringing BUZZER is a differnt experience. I become success in first try for ringing the buzzer yeah! i love that buzzer sound.  By attending this bootcamp i've learned lot of things such us more about adriuno and connection circuit etc...
the major thing given by this bootcamp is that i become inspired to do more experiemnts in iot.*

# **IOT Bootcamp Challenges**
### **Assignment 1 - Automatic Night Lamp using LDR & LED**

![assignment 1](https://user-images.githubusercontent.com/81223681/132480345-65ad96c0-6bce-41df-83ac-9883cb95afca.jpg)
## Code
```ino
const int LED = 13;  
const int LDR = A0;  

void setup() {
  Serial.begin(9600);
  pinMode(LED, OUTPUT); 
  pinMode(LDR, INPUT);   
}

void loop()
{
  int ldrStatus = analogRead(LDR);  
  if (ldrStatus <= 400) {
    digitalWrite(LED, HIGH);               
    Serial.println("Room is DARK - LED ON");
  }
  else {
    digitalWrite(LED, LOW);         
    Serial.println("Room is BRIGHT - LED OFF");
    }
}
```
### **Assignment 2 - Digital Dice using 6 LEDs & 1 Push Button**

![assignment 2](https://user-images.githubusercontent.com/81223681/132691137-1dc0f6a6-185d-403c-bf45-9b230a1810c9.jpg)
## Code
```ino
int first = 2;
int second = 3;
int third = 4;
int fourth = 5;
int fifth = 6;
int sixth = 7;


int button = 12;
int pressed = 0;

void setup() {
  
  for (int i=first; i<=sixth; i++) {
    pinMode(i, OUTPUT);
  }
  
  pinMode(button, INPUT);
  
  
  randomSeed(analogRead(0));

  #ifdef DEBUG
    Serial.begin(9600);
  #endif

}

void buildUpTension() {
 for (int i=first; i<=sixth; i++) {
    if (i!=first) {
      digitalWrite(i-1, LOW);
    }
    digitalWrite(i, HIGH);
    delay(100);
  }
  // right to left
  for (int i=sixth; i>=first; i--) {
    if (i!=sixth) {
      digitalWrite(i+1, LOW);
    }
    digitalWrite(i, HIGH);
    delay(100);
  }
}

void showNumber(int number) {
  digitalWrite(first, HIGH);
  if (number >= 2) {
    digitalWrite(second, HIGH);
  }
  if (number >= 3) {
    digitalWrite(third, HIGH);    
  }
  if (number >= 4) {
    digitalWrite(fourth, HIGH);    
  }
  if (number >= 5) {
    digitalWrite(fifth, HIGH);    
  }
  if (number == 6) {
    digitalWrite(sixth, HIGH);    
  }
}

int throwDice() {
  
  int randNumber = random(1,7);
  
  #ifdef DEBUG
    Serial.println(randNumber);
  #endif
  
  return randNumber;
}

void setAllLEDs(int value) {
  for (int i=first; i<=sixth; i++) {
    digitalWrite(i, value);
  }
}

void loop() {
  
  pressed = digitalRead(button);

  if (pressed == HIGH) {
    
    setAllLEDs(LOW);
    
    buildUpTension();
    int thrownNumber = throwDice();
    showNumber(thrownNumber);
  } 

}
```
# IoT Bootcamp Level-2
## Experiment-1
#### Second level of IOT Challlenge starts with some basic blynk apps
*To be completed wait for it*

