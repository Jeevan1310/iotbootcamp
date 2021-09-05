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
# Experiment-8 **Flame Sensor**
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
# Experiment-9 **LM35 Temperature Sensor**
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
# Experiment-10 **IR Remote Control Using TSOP**
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
# Experiment-12 **7 Segment Display**
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
