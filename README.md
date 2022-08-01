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



#HUMIDITY AND TEMPERATURE SENSOR
#include <Adafruit_Sensor.h>
#include <DHT.h>;
#define DHTPIN D7 // what pin we're connected to
#define DHTTYPE DHT11 // DHT 22 (AM2302)
DHT dht(DHTPIN, DHTTYPE); //// Initialize DHT sensor for normal 16mhz Arduino
//Variables
int chk; float hum; //Stores humidity value
float temp; //Stores temperature value
void setup()
{
Serial.begin(9600);
dht.begin();
}
void loop()
{
delay(2000);
//Read data and store it to variables hum and temp
hum = dht.readHumidity();
temp= dht.readTemperature();
//Print temp and humidity values to serial monitor
Serial.print("Humidity: ");
Serial.print(hum);
Serial.print(" %, Temp: ");
Serial.print(temp);
Serial.println(" Celsius");
delay(1000); //Delay 2 sec.
}
