# Ilya Glovatskiy
**Male <br>
Date of birth: 15.04.1983**
## Contacts ##
Tel: [+79129223939](tel://+79129223939) <br>
email: [ilia83@gmail.com](mailto:ilia83@gmail.com) <br>
Telegram: [Baton72](https://t.me/Baton72)

## Education ##
**2000-2006** <br> 
*Tyumen state oil and gas university* <br>
Qualified as oil and gas engineer 

## About me ##
I've got first PC in 1991. It was no studying or something else, just games, but computers started to be a point of interest. <br>
Started work career at 2001 as a technician in oil gas ans water treatment department. In parallel served a network of 20 computers and a telephony for 20 users. <br>
After 20 years started to work as a programmer and now creating an ERP for small oil and gas research company.

## Skills ##
* HTML
* CSS
* PHP
* Arduino
* bash
* JavaScript

## Code example ##
```
ESP8266WebServer server(80);

void SendCommandToTable()
{
  RotationAngle = 360 / (StepsNumber.toInt());
  Serial.println("Sending command.");
  Serial.println("CT+START(1,1,0," + String(RotationAngle) + ",0,1);\r\n");
  //client.print("CT+TRUNSINGLE(1,"+StepsNumber+");\r\n");
  client.print("CT+START(1,1,0," + String(RotationAngle) + ",0,1);\r\n");
}

void listenTotable()
{
  while (TableStopped != 1)
  {
    while (client.available())
    {
      String clirx = client.readStringUntil('\;');
      Serial.println("Recieving: " + clirx);
      if (clirx == ("CR+EVENT=TB_END"))
      {
        Serial.println("Table ended");
        TableStopped = 1;
      };
    }
    String clirx = "";
    //delay (10000);
  }
}

void RunSequence()
{
  for (int i = 0; i < StepsNumber.toInt(); i++)
  {
    TableStopped = 0;
    SendCommandToTable();
    //we need to check table state to 1
    while (TableStopped != 1)
    {
      unsigned long timing;
      if (millis() - timing > 1000)
      { //you should choose pause duration instead of 1000
        timing = millis();
        Serial.println("1 second");
      }
      yield();
    }
    Serial.println("Flash goes here");
  }
}

```

## Finished projects ##
1. Car multimedia system using arduino, wi-fi router and smartphone. (https://www.youtube.com/watch?v=SJjIGl0NPb4)
2. Photogrammetry system using ESP32 controlling a turntable, 4 flashes and 3 cameras.
3. ESP32 controlled WiFi clock with a remote temperature and humidity sensor.
4. Mac-style "breathing" LED for PC using arduino. 

## Languages ##
English - A2