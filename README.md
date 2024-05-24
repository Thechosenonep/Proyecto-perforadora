# Proyecto-perforadora
BOXMARK
Proyecto perforadora 

Para ajustar la hora del RTC , por favor ejecute el siguiente código 

#include <Wire.h>
#include <RTClib.h>

RTC_DS1307 rtc;

void setup() {
  Serial.begin(9600);
  if (!rtc.begin()) {
    Serial.println("No se pudo encontrar el RTC");
    while (1);
  }

  // Ajustar el RTC con la fecha y hora de compilación
  rtc.adjust(DateTime(F(__DATE__), F(__TIME__)));
  Serial.println("RTC ajustado a la hora de compilación.");

  // Imprimir la fecha y hora actuales para verificación
  DateTime now = rtc.now();
  Serial.print("Fecha y hora actual: ");
  Serial.print(now.year(), DEC);
  Serial.print('/');
  Serial.print(now.month(), DEC);
  Serial.print('/');
  Serial.print(now.day(), DEC);
  Serial.print(" ");
  Serial.print(now.hour(), DEC);
  Serial.print(':');
  Serial.print(now.minute(), DEC);
  Serial.print(':');
  Serial.print(now.second(), DEC);
  Serial.println();
}

void loop() {
  // Solo para visualizar la hora continuamente en el monitor serial
  DateTime now = rtc.now();
  Serial.print("Fecha y hora actual: ");
  Serial.print(now.year(), DEC);
  Serial.print('/');
  Serial.print(now.month(), DEC);
  Serial.print('/');
  Serial.print(now.day(), DEC);
  Serial.print(" ");
  Serial.print(now.hour(), DEC);
  Serial.print(':');
  Serial.print(now.minute(), DEC);
  Serial.print(':');
  Serial.print(now.second(), DEC);
  Serial.println();

  delay(1000);  // Esperar un segundo antes de actualizar
}

Después suba el código principal
