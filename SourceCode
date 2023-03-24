//Didapatkan dari Blynk setelah Membuat Template Kontrol lampu
#define BLYNK_PRINT Serial
#define BLYNK_TEMPLATE_ID "TMPL63S3ixlNy"
#define BLYNK_TEMPLATE_NAME "Kontrol Lampu"
#define BLYNK_AUTH_TOKEN "iMdxZ61WurI2SIbDmmSeOcZTmX35HZh7"

#include <WiFi.h>
#include <WiFiClient.h>
#include <BlynkSimpleEsp32.h>

char auth[] = BLYNK_AUTH_TOKEN;
char ssid[] = "Wokwi-GUEST";
char pass[] = "";

BlynkTimer timer;

#define LED1 12
#define LED2 13
int SW_State=0;

BLYNK_WRITE (V0)
{
  SW_State = param.asInt();
  if (SW_State == 1)
  {
    digitalWrite(LED1, HIGH);
    Serial.println("LAMPU NYALA");
    Blynk.virtualWrite(V0, HIGH);
  }

  else
  {
    digitalWrite(LED1, LOW);
    Serial.println("LAMPU MATI");
    Blynk.virtualWrite(V0, LOW);
  }
}

BLYNK_WRITE (V1)
{
  SW_State = param.asInt();
  if (SW_State == 1)
  {
    digitalWrite(LED2, HIGH);
    Serial.println("LAMPU NYALA");
    Blynk.virtualWrite(V0, HIGH);
  }

  else
  {
    digitalWrite(LED2, LOW);
    Serial.println("LAMPU MATI");
    Blynk.virtualWrite(V1, LOW);
  }
}

void setup()
{
  pinMode(LED1, OUTPUT);
  pinMode(LED2, OUTPUT);
  Serial.begin(9600);
  Blynk.begin(auth, ssid, pass);
}

void loop()
{
  Blynk.run();
  timer.run();
}
