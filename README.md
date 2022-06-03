# Esp32-Bluetooth

```c++
#include "BluetoothSerial.h"
BluetoothSerial SerialBT;

void setup()
{
  Serial.begin(9600); //puerto serial del esp32
  SerialBT.begin("Esp32"); //nombre del dispositivo
}

void loop()
{
  if(Serial.available()) //si recibe datos del puerto serial
  {
    SerialBT.write(Serial.read()); //manda los datos
  }
  if(SerialBT.available()) //si recibe datos 
  {
    Serial.write(SerialBT.read()); //escribe los datos en el puerto serial
  }
}
```
