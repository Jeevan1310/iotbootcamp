# IOT Bootcamp
# About me
My name is **JEEVAN JOSEPH**  I am studying BCA at Kristu Jyoti College of Management and Technology, Changanassery I joined this bootcamp because i am a noobie to IOT. I don't know what to do in iot so when i got this oppurtunity i started learning iot .

# Experiment-1 **Hello world Led blinking**
![Hello world Led blinking](https://myoctocat.com/assets/images/base-octocat.svg)
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
### Errors
*As a Noobie I don't know what to do in IOT when i connecting bulb to the breadboard it does not glow i tried more but the led doesnot glow then i give it to direct connection it glow and exploded but later come to know that it was my mistake in connecting the wire wrongly*

# Experiment-2 **Traffic Light**
![Traffic Light](https://myoctocat.com/assets/images/base-octocat.svg)
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
![LED Chasing Effect](https://myoctocat.com/assets/images/base-octocat.svg)
## code




    
