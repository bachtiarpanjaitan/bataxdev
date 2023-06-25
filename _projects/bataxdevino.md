---
title: "Bataxdevino"
excerpt: "Bataxdev Library For More Module Of arduino using C++"
header:
  image: /assets/images/library.jpg
  teaser: /assets/images/library.jpg
  overlay_image: /assets/images/unsplash-image-2.jpg
  og_image: /assets/images/library.jpg
  actions:
    - label: "View on Github"
      url: "https://github.com/bachtiarpanjaitan/Bataxdevino"
share: true
categories:
  - Library
tags:
  - C++
  - Arduino
---

**How to use it ?**
- Import Bataxdevino library on your .ino file 
```
#include <Bataxdevino.h>
```
- Create a new variable of Bataxdevino library

```
Bataxdevino btx;
```
- Then use it

**Available Method**
Show text on LCD screen 16*2
  
```
  //import Library LiquidCrystal first
  LiquidCrystal lcd (RS,EN,d4,d5,d6,d7);
  ...
  lcd.begin(16,2);
  btx.lcdPrint(lcd,0,0,"your text here",true);
  ...
```
Read LCD Button 16*2

```
 //first initialize LCD
 const int buttonPin = 0;
 lcd.begin(16,2);

 btx.readLcdButton(buttonPin);
```
For special case, sometime you need convert an integer value into char and then you can use it.

```
//define variable char first
char yourChar[3];
yourChar = btx.intToChar(yourIntegerValue)
```