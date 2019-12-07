# report
```
#include <Servo.h>
#include <SoftwareSerial.h>
Servo sr;
SoftwareSerial mySerial(10, 11);
String myString="";
void setup(){
  mySerial.begin(9600);
}

void loop(){
  while(mySerial.available()) {
    char myChar = (char)mySerial.read();
    myString+=myChar;
    delay(5);
  }
  if(!myString.equals("")) {
    Serial.println("input value: "+myString);
     if(myString=="1") {
      sr.attach(12);
      sr.write(1300);
      delay(666);
      sr.write(1700);
      delay(550);
      sr.detach();
    }
    myString = "";
  }
}
```
