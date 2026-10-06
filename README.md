# Image Morse Codec

![PHP Version](https://img.shields.io/badge/PHP-%3E%3D8.5-blue.svg?logo=php)
![PHP GD Extension](https://img.shields.io/badge/GD%20extension-required-orange)
![License](https://img.shields.io/badge/license-Apache%202.0-green.svg)
[![Stand with Ukraine](https://raw.githubusercontent.com/vshymanskyy/StandWithUkraine/main/badges/StandWithUkraine.svg)](https://stand-with-ukraine.pp.ua)
[![Made in Ukraine](https://img.shields.io/badge/made_in-Ukraine-ffd700.svg?labelColor=0057b7)](https://stand-with-ukraine.pp.ua)

**Turn images into Morse code — and back again!** 📡✨

Image Morse Codec is a lightweight educational and experimental PHP library that encodes image pixel data into Morse code and reconstructs images from the resulting text files.

The project explores a simple question:

> What happens when image data is represented using Morse code?

It supports PNG and JPEG images through PHP's GD extension.

> ⚠️ **Experimental project:** Morse code is intentionally used as the data representation. The resulting files are significantly less compact than conventional image formats.

---

## ✨ Features

- ⚡ **Lightweight** — built with native PHP and GD.
- 🧩 **Simple API** — two main methods: `toMorse()` and `fromMorse()`.
- 🔄 **Bidirectional** — encode images to Morse text and decode them back.
- 🎨 **PNG and JPEG support**.
- 📡 **Morse-based representation** — image pixel data is serialized as Morse code.
- 🧪 **Educational and experimental** — designed to explore encoding, serialization, and image reconstruction.

---

## ⚡ Requirements

- PHP **>= 8.5**
- PHP **GD extension** enabled

---

## 📖 Usage

### Encode image → Morse

```php
<?php

require_once 'ImageMorseCodec/ImageMorseCodec.php';

use ImageMorseCodec\ImageMorseCodec;

$codec = new ImageMorseCodec();

// Provide an image filename or a full path.
$codec->toMorse('example.png');
```

This creates:

```text
example.txt
```

### Decode Morse → image

```php
<?php

require_once 'ImageMorseCodec/ImageMorseCodec.php';

use ImageMorseCodec\ImageMorseCodec;

// Provide a Morse text filename or a full path.
$codec = new ImageMorseCodec();

$codec->fromMorse('example.txt');
```

The image is reconstructed using the image format and dimensions stored in the Morse file.

---

## 🧠 How It Works

The codec processes an image pixel by pixel.

The basic pipeline is:

```text
Image
  ↓
GD
  ↓
Pixel color data
  ↓
Decimal digits
  ↓
Morse code
  ↓
Text file
```

Decoding reverses the process:

```text
Text file
  ↓
Morse code
  ↓
Decimal values
  ↓
Pixel color data
  ↓
GD image
```

Image metadata such as format, width, and height is stored in the encoded data so the image can be reconstructed later.

---

## ⚠️ Limitations

Image Morse Codec is intentionally experimental and is not intended to replace established image codecs such as PNG, JPEG, WebP, or AVIF.

Because Morse code represents every decimal digit using five Morse symbols, the encoded text can become very large.

Large images may therefore:

- require significant amounts of memory;
- take longer to encode or decode;
- produce very large text files.

JPEG also remains a lossy image format. Reconstructing a JPEG image does not imply byte-for-byte preservation of the original JPEG file.

---

## 💡 Inspiration

This project was inspired by the legacy of **Samuel Morse (1791–1872)**, whose work on Morse code helped establish a practical system for long-distance communication.

As a software developer, I wanted to explore a small and unusual idea: representing visual information using Morse code.

The project is an experiment in data representation, image processing, and reversible transformation.

This library is my small tribute to that idea.

---

## 👨‍💻 Author

- [Oleh Kovalenko](https://github.com/oleh-exe) — Owner & Maintainer

---

## 📜 License

[Apache License 2.0](LICENSE)