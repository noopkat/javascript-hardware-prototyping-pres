footer: @noopkat, 2014
slidenumbers: true

# Your Own JavaScript Army
## (prototyping devices doesn't have to suck)

---

# Suz Hinton
## hardware enthusiast

---

# If you dare

```
git clone https://github.com/noopkat/blend-micro-io.git
npm install
node test.js
```

---

# ...
## I like to make stuff

---
# ...
## I like to make **fun** stuff

---

![](https://camo.githubusercontent.com/928f51bf4ef96487fc791ace37bbae47b9e6367b/687474703a2f2f662e636c2e6c792f6974656d732f306c325a32553374303233463154324a314432312f7477696e7365742e6a7067)

---

![](https://camo.githubusercontent.com/3dc80e1c3ff6e5750aaf6d74325aefcda7c854df/687474703a2f2f662e636c2e6c792f6974656d732f314d3275336f3043324c31723045316b335532522f70757272322e6a7067)

---

![](https://raw.githubusercontent.com/noopkat/nerd-docs/master/img/meowbox.jpg)

---


# IoT

- Application code
- Data
- Security

---

# IoT

- Application code
- Data
- Security
- **Devices**

---

# ...

# Internet of Things

---

# ...

# Internet of **Things**

---

# ...

# Building hardware

---

# ...

# Building **hard**ware

---

# Standard Prototyping Workflow

1. Arduino

---

# Standard Prototyping Workflow

1. Arduino
2. Sensors/hardware

---

# Standard Prototyping Workflow

1. Arduino
2. Sensors/hardware
3. Write C, or loosely related language

---

# Standard Prototyping Workflow

1. Arduino
2. Sensors/hardware
3. Write C, or loosely related language
4. Write -> compile -> upload

---

# Standard Prototyping Workflow

1. Arduino
2. Sensors/hardware
3. Write C, or loosely related language
4. **Write -> compile -> upload**
5. **Write -> compile -> upload**
6. **Write -> compile -> upload**

---

# More Pain

- Dependency management
- fragmented library sources

---

# (╯°□°)╯︵ ┻━┻
# (╯°□°)╯︵ ┻━┻
# (╯°□°)╯︵ ┻━┻
# (╯°□°)╯︵ ┻━┻

---

# ...
# (this is actually supposed to be more fun)

---

# NodeJS

- JavaScript runtime
- both in and out of browser
- small module mentality

---

# Johnny-Five

- Robotics and other hardware in NodeJS
- Easy to use API
- Fast to get up and running with Arduino

---

# Getting started

```
npm install johnny-five
```

---

# Getting started

```javascript
var five = require("johnny-five"),
    board = new five.Board();

board.on("ready", function() {
  // do Arduino things here
});
```

---

# The 'Hello World' of hardware

```javascript
var five = require("johnny-five"),
    board = new five.Board();

board.on("ready", function() {
  
  var myLed = new five.Led(13);
  myLed.strobe();

});
```

---

# Can I prototype "real things" with this?

---

# Can I prototype "real things" with this?

# - yes!

---

# What's in an off the shelf device?

![inline](https://d3nevzfk7ii3be.cloudfront.net/igi/DDanqPmUH4IJBBJo)

---

# Fitness Device

1. 3 axis accelerometer


---

# Fitness Device

1. 3 axis accelerometer
2. Vibration motor

---

# Fitness Device

1. 3 axis accelerometer
2. Vibration motor
3. OLED screen

---

# Fitness Device

1. 3 axis accelerometer
2. Vibration motor
3. OLED screen
4. Battery

---

# Fitness Device

1. 3 axis accelerometer
2. Vibration motor
3. OLED screen
4. Battery
5. Bluetooth enabled micro-controller

---

# Fitness Device

1. **3 axis accelerometer**
2. Vibration motor
3. **OLED screen**
4. Battery
5. **Bluetooth enabled micro-controller**

---

# Accelerometer

```javascript
board.on("ready", function() {

  var accel = new five.Accelerometer({
    pins: ["A3", "A4", "A5"],
    sensitivity: 96, // mV/degree/seconds
    zeroV: 478 // volts in ADC
  });

  accel.on("data", function(data) {
    console.log("raw: ", data);
  });

```

---


![inline](http://www.analog.com/library/analogdialogue/archives/44-06/AD44_06_FIG_01.jpg)

credit: analog.com

---

![inline fill](http://www.analog.com/library/analogdialogue/archives/44-06/AD44_06_FIG_02.jpg)

credit: analog.com

---

# OLED display

```javascript
var Oled = require("oled-js");

board.on("ready", function() {

  var oled = new Oled(board, five, 128, 32, 0x3C, "I2C");

});
```

---

# Bluetooth Low Energy

```javascript
var BLEFirmata = require("./");

var board = new five.Board({
  io: new BLEFirmata({"name": "BlendMicro"})
});

board.on("ready", function() {
  // carry on as normal here
});
```

---

# ...

# Building **hard**ware

---

# ...

# Don't let hardware scare you

![](https://farm1.staticflickr.com/3/5164271_2f583028d6_o.jpg)

#### photo credit: jmorgan via Flickr
---

# ...

# Build things for the fun of it

---

# ...

# (Thank you)

