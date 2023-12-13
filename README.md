# ArduinoPet

```C++
    #include <NewPing.h>
    #include <Servo.h>

    #define TRIGGER_PIN  10
    #define ECHO_PIN     11
    #define MAX_DISTANCE 400
     
    NewPing sonar(TRIGGER_PIN, ECHO_PIN, MAX_DISTANCE);
    Servo myservo;
     
    void setup() {
      Serial.begin(9600);
      myservo.attach(9);  // сервопривод на выводе 9
    }
     
    void loop() {
      delay(50);
      Serial.print("Ping: ");
      Serial.print(sonar.ping_cm());
      Serial.println("cm");
      int val = sonar.ping_cm();
      Serial.println(val);
      if (val > 3 && val < 7){
        myservo.write(180);
        delay(50);
      }
    }
```
