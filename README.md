# 33112_LED_RVB_GROVE

LED RGB GROVE [33112](https://www.pierron.fr/interface-arduino-uno-5949.html)
Caractéristiques techniques :
- Alimentation : 5 V
- Consommation : 20 mA
- Couleur : RVB

![33188](/img/L-33112.jpg)

# Exemple :
### Arduino / C++
```cpp
#include <ChainableLED.h>

#define NUM_LEDS  5

ChainableLED leds(7, 8, NUM_LEDS);

void setup()
{
  leds.init();
}

float hue = 0.0;
boolean up = true;

void loop()
{
  for (byte i=0; i<NUM_LEDS; i++)
    leds.setColorHSL(i, hue, 1.0, 0.5);
    
  delay(50);
    
  if (up)
    hue+= 0.025;
  else
    hue-= 0.025;
    
  if (hue>=1.0 && up)
    up = false;
  else if (hue<=0.0 && !up)
    up = true;
}
```
## À propos :

PIERRON ASCO-CELDA (https://www.pierron.fr/).
