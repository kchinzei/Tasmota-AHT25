# Tasmota-AHT25

Private UserMod for Tasmota

It's a usermod of [Tasmota](https://tasmota.github.io/docs/) for ESP8266 with small (< 2MB) flash.
PCA9xxx is an I2C based PWM controller chips from NXP.

At this moment I don't have a plan to ask a pull request, because it's experimental.

## Build it

Basically, this repository keeps its own files apart from [Tasmota](https://tasmota.github.io/docs/) files.
This makes following updates in Tasmota easy.
But you need to place the files into proper places before building Tasmota.

- Copy `platformio_tasmota_cenv.ini` to `Tasmota`
- Copy `user_config_override.h` to `Tasmota/tasmota`

Overwrite existing one if there is. In Linux or macOS you can also use `ln` terminal command so that any changes to these files inside `Tasmota` folder will be visible by git commands.

This modification is intended to
- Make binary small so that it can do OTA on 2MB flash ESP8266.
From experience, you need to make gzip'ed binary less than 500 kB.
- Enable AHT-25 temp/humid sensor.
- Enable Ikea Vindriktning air quality sensor.

See [Compiling](https://tasmota.github.io/docs/Compile-your-build/#customize-your-build) for detail.

## License

MIT License

Copyright (c) 2022 Kiyo Chinzei (kchinzei@gmail.com)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
