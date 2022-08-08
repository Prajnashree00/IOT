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




//LDR sensor
int ldr=A0;//Set A0(Analog Input) for LDR.
 int value=0;
 int led=D1;
 void setup() {
 Serial.begin(9600);
 pinMode(led,OUTPUT);
 }

 void loop() {
 value=analogRead(ldr);//Reads the Value of LDR(light).
 Serial.println("LDR value is :");//Prints the value of LDR to Serial Monitor.
 Serial.println(value);
 if(value<50)
   {
     digitalWrite(led,HIGH);//Makes the LED glow in Dark.
   }
   else
   {
     digitalWrite(led,LOW);//Turns the LED OFF in Light.
   }
   delay(1000);
 }
 
 
 RGB
 
 int red = D1;
 int green = D6;
 int blue = D7;
 //GROUND IS CONNECTED TO 3V 
 void setup() {
   pinMode(red, OUTPUT);
   pinMode(green, OUTPUT);
   pinMode(blue, OUTPUT);

 }

 void loop() {
   displayColor(0b100); //RED
   delay(1000);
   displayColor(0b010); //GREEN
   delay(1000);
   displayColor(0b001); //BLUE
   delay(1000);
   displayColor(0b101); //MAGENTA
   delay(1000);
   displayColor(0b011); //CYAN
   delay(1000);
   displayColor(0b110); //YELLOW
   delay(1000);
   displayColor(0b111); //WHITE
   delay(1000);
 }

 void displayColor(byte color) {
   digitalWrite(red, !bitRead(color, 2));
   digitalWrite(green, !bitRead(color, 1));
   digitalWrite(blue, !bitRead(color, 0));
 }


IR_LED
  int ir=D7;
 int led=D5;
 void setup() {
   // put your setup code here, to run once:
   pinMode(ir,INPUT);
     pinMode(led,OUTPUT);
     Serial.begin(9600);

 }

 void loop() {
   // put your main code here, to run repeatedly:
   int irvalue=digitalRead(ir);
   if(irvalue==LOW)
   {
     Serial.println("LOW");
     digitalWrite(led,HIGH);
   }
   else
   {
     Serial.println("HIGH");
     digitalWrite(led,LOW);
   }
 delay(100);
 }
</br>
</br>
</br>
     LDR
     const int ldrPin=A0;
     void setup() {
       Serial.begin(9600);
       pinMode(ldrPin,INPUT);
     }
     void loop() {
       int rawData = analogRead(ldrPin);   
       Serial.println(rawData);
       delay(1000);
     }
</br>
</br>
</br>
//6 led
   int pinsCount=6;                        // declaring the integer variable pinsCount
   int pins[] = {D4,D2,D3,D5,D6,D7};          // declaring the array pins[]

   void setup() {                
     for (int i=0; i<pinsCount; i=i+1){    // counting the variable i from 0 to 9
       pinMode(pins[i], OUTPUT);            // initialising the pin at index i of the array of pins as OUTPUT
     }
   }

   void loop() {
     for (int i=0; i<pinsCount; i=i+1){    // chasing right
       digitalWrite(pins[i], HIGH);         // switching the LED at index i on
       delay(100);                          // stopping the program for 100 milliseconds
       digitalWrite(pins[i], LOW);          // switching the LED at index i off
     }
    for (int i=pinsCount-1; i>0; i=i-1){   // chasing left (except the outer leds)
       digitalWrite(pins[i], HIGH);         // switching the LED at index i on
       delay(100);                          // stopping the program for 100 milliseconds
     digitalWrite(pins[i], LOW);          // switching the LED at index i off
    }
   }
</br>
