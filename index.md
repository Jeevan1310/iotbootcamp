# IOT Bootcamp
# About me
My name is **JEEVAN JOSEPH**  I am studying BCA at Kristu Jyoti College of Management and Technology, Changanassery I joined this bootcamp because i am a noobie to IOT. I don't know what to do in iot so when i got this oppurtunity i started learning iot .

# Experiment-1 **Hello world Led blinking**
![Hello world Led blinking]()
## code
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
### Experience
*As a Noobie I don't know what to do in IOT when i connecting bulb to the breadboard it does not glow i tried more but the led doesnot glow then i give it to direct connection it glow and exploded but later come to know that it was my mistake in connecting the wire wrongly*

# Experiment-2 **Traffic Light**
![Traffic Light]()
## code
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
![LED Chasing Effect]()
## code
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
![Button Controlled LED]()
## code
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
### Experience
*In here i got bit confused how to connect button in breaadboard so i googled it and it become success*

# Experiment-5 **Buzzer**
![Buzzer]()
## code
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
## Experience
*Ringing BUZZER is a differnt experience. I become success in first try for ringing the buzzer yeah! i love that buzzer sound*

# Experiment-6 **RGB LED**
![RGB LED]()
## code
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
![LDR Light Sensor]()
## code
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
![Flame Sensor()
## code
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
![LM35 Temperature Sensor]()
## code
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
   irrecv.enableIRIn();
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
```
# Experiment-10 **IR Remote Control Using TSOP**
![IR Remote Control Using TSOP]()
## code
```ino
int potpin=0;
int ledpin=13;
int val=0;
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
# Experiment-12 **7 Segment Display**
![7 Segment Display]()
## code
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
```
