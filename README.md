# IOT

https://wokwi.com/projects/335586982610600531 :led

https://wokwi.com/projects/333715360946586195   1

https://wokwi.com/projects/333715360946586195 :- Traffic led<br> 

https://wokwi.com/projects/333801426044060243  :-RGB LEDK<br> 

https://wokwi.com/projects/333805190238962259  :-RGB LED2<br>

https://wokwi.com/projects/322062421191557714 :- hello wokwi<br>

https://create.arduino.cc/projecthub/SURYATEJA/use-a-buzzer-module-piezo-speaker-using-arduino-uno-89df45- basic buzzer explaination<br>

https://wokwi.com/projects/334977593624232530 : servo motar 

https://wokwi.com/projects/334977593624232530  :-    servo motar using for loop

https://wokwi.com/projects/334982677972124242  :- servometer with potentiometer slide 

https://wokwi.com/projects/335702826545054292  :-servomotar with pushbutton

https://wokwi.com/projects/335065707348755026  :-buzzer 

https://wokwi.com/projects/335068168319926866  :buzzer with button 

https://wokwi.com/projects/335131064102027860 :- ultrasonic sensor 

https://wokwi.com/projects/335070056491778642  :- ULTRASONIC WITH BUZZER 10(1)
 
https://wokwi.com/projects/335585334716793427   :- Ultrasonic with buzzer (2)

https://wokwi.com/projects/335075055329346132   :- varring with intensity ultrasonic sensor

https://wokwi.com/projects/335611619397599827 :-varring with distance using led

https://wokwi.com/projects/335616878141506130  :-two ultrasonic sensor

https://wokwi.com/projects/335701700267475540  :-potentiometer using led(extra)

https://wokwi.com/projects/335702196478804564  :-potentiometer using led


lab list:
https://wokwi.com/projects/337602028014404178 -1<br>
https://wokwi.com/projects/337602684471214674 -2(humidity sensor and temperature sensor using buttton)
https://wokwi.com/projects/337604296859189842 -3(humidity sensopr and temperature using LCD)<br>



#HUMIDITY AND TEMPERATURE SENSOR<br>
#include <Adafruit_Sensor.h><br>
#include <DHT.h>;<br>
#define DHTPIN D7 // what pin we're connected to<br>
#define DHTTYPE DHT11 // DHT 22 (AM2302)<br>
DHT dht(DHTPIN, DHTTYPE); //// Initialize DHT sensor for normal 16mhz Arduino<br>
//Variables<br>
int chk; float hum; //Stores humidity value<br>
float temp; //Stores temperature value<br>
void setup()<br>
{<br>
Serial.begin(9600);<br>
dht.begin();<br>
}<br>
void loop()<br>
{<br>
delay(2000);<br>
//Read data and store it to variables hum and temp<br>
hum = dht.readHumidity();<br>
temp= dht.readTemperature();<br>
//Print temp and humidity values to serial monitor<br>
Serial.print("Humidity: ");<br>
Serial.print(hum);<br>
Serial.print(" %, Temp: ");<br>
Serial.print(temp);<br>
Serial.println(" Celsius");<br>
delay(1000); //Delay 2 sec.<br>
}<br>




//LDR sensor<br>
int ldr=A0;//Set A0(Analog Input) for LDR.<br>
 int value=0;<br>
 int led=D1;<br>
 void setup() {<br>
 Serial.begin(9600);<br>
 pinMode(led,OUTPUT);<br>
 }<br>

 void loop() {<br>
 value=analogRead(ldr);//Reads the Value of LDR(light).<br>
 Serial.println("LDR value is :");//Prints the value of LDR to Serial Monitor.<br>
 Serial.println(value);<br>
 if(value<50)<br>
   {<br>
     digitalWrite(led,HIGH);//Makes the LED glow in Dark.<br>
   }<br>
   else<br>
   {<br>
     digitalWrite(led,LOW);//Turns the LED OFF in Light.<br>
   }<br>
   delay(1000);<br>
 }<br>
 
 
 RGB<br>
 
 int red = D1;<br>
 int green = D6;<br>
 int blue = D7;<br>
 //GROUND IS CONNECTED TO 3V <br>
 void setup() {<br>
   pinMode(red, OUTPUT);<br>
   pinMode(green, OUTPUT);<br>
   pinMode(blue, OUTPUT);<br>

 }<br>

 void loop() {<br>
   displayColor(0b100); //RED<br>
   delay(1000);<br><br>
   displayColor(0b010); //GREEN<br><br>
   delay(1000);<br><br>
   displayColor(0b001); //BLUE<br><br>
   delay(1000);<br><br>
   displayColor(0b101); //MAGENTA<br><br>
   delay(1000);<br><br>
   displayColor(0b011); //CYAN<br><br>
   delay(1000);<br><br>
   displayColor(0b110); //YELLOW<br><br>
   delay(1000);<br><br>
   displayColor(0b111); //WHITE<br><br>
   delay(1000);<br><br>
 }<br><br>

 void displayColor(byte color) {<br><br>
   digitalWrite(red, !bitRead(color, 2));<br><br>
   digitalWrite(green, !bitRead(color, 1));<br><br>
   digitalWrite(blue, !bitRead(color, 0));<br><br>
 }<br><br>


IR_LED<br><br>
  int ir=D7;<br><br>
 int led=D5;<br><br>
 void setup() {<br><br>
   // put your setup code here, to run once:<br><br>
   pinMode(ir,INPUT);<br>
     pinMode(led,OUTPUT);<br>
     Serial.begin(9600);<br>

 }<br>

 void loop() {<br>
   // put your main code here, to run repeatedly:<br>
   int irvalue=digitalRead(ir);<br>
   if(irvalue==LOW)<br>
   {<br>
     Serial.println("LOW");<br>
     digitalWrite(led,HIGH);<br>
   }<br>
   else<br>
   {<br>
     Serial.println("HIGH");<br>
     digitalWrite(led,LOW);<br>
   }<br>
 delay(100);<br>
 }<br>
</br><br>
</br><br>
</br><br>
     LDR<br>
     const int ldrPin=A0;<br>
     void setup() {<br>
       Serial.begin(9600);<br>
       pinMode(ldrPin,INPUT);<br>
     }<br>
     void loop() {
       int rawData = analogRead(ldrPin);<br>   
       Serial.println(rawData);<br>
       delay(1000);<br>
     }<br>
</br><br>
</br><br>
</br><br>
//6 led<br>
   int pinsCount=6;                        // declaring the integer variable pinsCount<br>
   int pins[] = {D4,D2,D3,D5,D6,D7};          // declaring the array pins[]<br>

   void setup() {     <br>           
     for (int i=0; i<pinsCount; i=i+1){    // counting the variable i from 0 to 9<br>
       pinMode(pins[i], OUTPUT);            // initialising the pin at index i of the array of pins as OUTPUT<br>
     }<br>
   }<br>

   void loop() {<br>
     for (int i=0; i<pinsCount; i=i+1){    // chasing right<br>
       digitalWrite(pins[i], HIGH);         // switching the LED at index i on<br>
       delay(100);                          // stopping the program for 100 milliseconds<br>
       digitalWrite(pins[i], LOW);          // switching the LED at index i off<br>
     }
    for (int i=pinsCount-1; i>0; i=i-1){   // chasing left (except the outer leds)<br>
       digitalWrite(pins[i], HIGH);         // switching the LED at index i on<br>
       delay(100);                          // stopping the program for 100 milliseconds<br>
     digitalWrite(pins[i], LOW);          // switching the LED at index i off<br>
    }<br>
   }<br>
</br><br>

:led chaser
https://wokwi.com/projects/340774241535263315 :led chaser<br>
 https://wokwi.com/projects/340778876526395987 :ldr<br>
 https://wokwi.com/projects/340780447593136722:ir reciver
