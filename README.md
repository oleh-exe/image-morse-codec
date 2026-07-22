# Image Morse Codec

![PHP Version](https://img.shields.io/badge/PHP-%3E=8.2-blue.svg?logo=php)
![PHP GD Extension](https://img.shields.io/badge/GD%20extension-required-orange)
![License](https://img.shields.io/badge/license-Apache%202.0-green.svg)
[![Stand with Ukraine](https://raw.githubusercontent.com/vshymanskyy/StandWithUkraine/main/badges/StandWithUkraine.svg)](https://stand-with-ukraine.pp.ua)
[![Made in Ukraine](https://img.shields.io/badge/made_in-Ukraine-ffd700.svg?labelColor=0057b7)](https://stand-with-ukraine.pp.ua)

**Turn images into Morse code — and back again!** 📡✨  
Image Morse Codec is a lightweight PHP library that encodes every pixel of a PNG or JPEG image into Morse code and saves it to a text file. You can also decode such files to reconstruct the original image.

⚠️ **Warning:** Processing large images may require a lot of RAM!

---

## ✨ Features
- ⚡ **Lightweight & fast**
- 🧩 **Simple API** — just two methods: `toMorse()` and `fromMorse()`
- 🔄 **Bidirectional** — convert images → text and text → images
- 🎨 **Supports PNG and JPEG (JPG)**

---

## ⚡ Requirements
- PHP **>= 8.2**
- PHP **GD extension** enabled

---

## 📖 Usage

### Encode image → Morse
```php
<?php

require_once('ImageMorseCodec/ImageMorseCodec.php');

use ImageMorseCodec\ImageMorseCodec;

$codec = new ImageMorseCodec();

// Instead of "example.png", provide the image name or full path
$codec->toMorse('example.png');
```

### Decode Morse → image
```php
<?php

require_once('ImageMorseCodec/ImageMorseCodec.php');

use ImageMorseCodec\ImageMorseCodec;

$codec = new ImageMorseCodec();

// Instead of "example.txt", provide the text file name or full path
$codec->fromMorse('example.txt');
```

---

## 💡 Inspiration

This project was inspired by the legacy of Samuel Morse (1791–1872), whose work on the Morse code helped lay the foundation for long-distance communication.

As a software developer, I wanted to explore a small but creative idea: representing visual information using one of the earliest digital communication systems ever created.

This library is my tribute to that idea.

---

## 👨‍💻 Author
- [Oleh Kovalenko](https://github.com/oleh-exe) — Owner & Maintainer

---

## 📜 License
[Apache 2.0](LICENSE)