# Image Morse Codec — Roadmap

This roadmap describes the planned evolution of Image Morse Codec as a small educational and experimental PHP library.

The project intentionally keeps its core idea simple:

> Encode image pixel data as Morse code and decode it back into an image.

The goal is not to compete with conventional image codecs, but to explore how visual data can be represented, serialized, and reconstructed using Morse code.

---

## 1. PHP 8.5 Upgrade

**Branch:** `chore/upgrade-php-8.5`

- [ ] Update the minimum supported PHP version to `8.5`.
- [ ] Review the codebase for PHP 8.5 compatibility.
- [ ] Remove or update obsolete constructs where appropriate.
- [ ] Improve type declarations where they increase correctness or readability.
- [ ] Review PHPDoc and method signatures.
- [ ] Update development tooling and CI configuration.
- [ ] Run the full test suite on PHP 8.5.
- [ ] Update README and documentation.

---

## 2. Correctness and Validation

Strengthen the codec against invalid or corrupted input.

- [ ] Validate the Morse file header.
- [ ] Validate the image format code.
- [ ] Validate image width and height.
- [ ] Validate Morse digit tokens.
- [ ] Validate the expected number of decoded pixels.
- [ ] Handle truncated or malformed Morse files gracefully.
- [ ] Return a consistent failure result for invalid input.
- [ ] Add regression tests for malformed files.

---

## 3. Round-Trip Testing

Verify that encoding and decoding preserve the intended pixel data.

- [ ] Add small PNG test images.
- [ ] Add truecolor PNG tests.
- [ ] Add transparency tests.
- [ ] Add palette-based PNG tests where supported.
- [ ] Add JPEG round-trip tests.
- [ ] Document the difference between pixel reconstruction and byte-for-byte file preservation.
- [ ] Test single-pixel and very small images.
- [ ] Test non-square images.
- [ ] Test larger images.

---

## 4. Memory Usage

Reduce unnecessary intermediate data structures.

Current processing creates several large arrays containing pixel and encoded data.

Possible improvements:

- [ ] Avoid keeping the entire pixel collection in memory where practical.
- [ ] Avoid unnecessary intermediate arrays.
- [ ] Investigate incremental Morse serialization.
- [ ] Investigate incremental decoding.
- [ ] Measure memory usage before and after optimization.
- [ ] Preserve readability while reducing memory consumption.

Optimization should remain secondary to correctness and maintainability.

---

## 5. Morse File Format

Document and stabilize the `.txt` representation.

- [ ] Define the file structure formally.
- [ ] Document metadata ordering.
- [ ] Document separators.
- [ ] Document pixel ordering.
- [ ] Document the valid Morse alphabet.
- [ ] Define malformed-input behavior.
- [ ] Consider a format version field if the format evolves incompatibly.

---

## 6. File Handling

Improve output and file lifecycle behavior.

- [ ] Ensure repeated `toMorse()` calls do not append duplicate data.
- [ ] Review input/output filename handling.
- [ ] Review file write error handling.
- [ ] Review image loading failures.
- [ ] Review image creation failures.
- [ ] Review output image write failures.

---

## 7. Internal Refactoring

Refactor only where it provides a clear benefit.

Potential areas:

- [ ] Separate Morse encoding/decoding logic from image handling.
- [ ] Reduce hidden state inside `ImageMorseCodec`.
- [ ] Simplify pixel traversal.
- [ ] Improve naming and method responsibilities.
- [ ] Remove unnecessary duplication.
- [ ] Preserve the existing public API where possible.

Avoid introducing unnecessary abstractions or dependencies.

---

## 8. Performance Experiments

Measure before optimizing.

- [ ] Benchmark encoding time.
- [ ] Benchmark decoding time.
- [ ] Benchmark memory consumption.
- [ ] Benchmark different image sizes.
- [ ] Compare different Morse serialization strategies.
- [ ] Document practical limitations.

The purpose of these experiments is to understand the codec, not to make unsupported performance claims.

---

## 9. Experimental Extensions

These are intentionally exploratory and may never become part of the stable API.

- [ ] Investigate alternative Morse serialization formats.
- [ ] Investigate more compact intermediate representations.
- [ ] Investigate streaming approaches.
- [ ] Investigate binary/Morse hybrid formats.
- [ ] Investigate additional image formats where GD support makes sense.
- [ ] Explore whether related encoding ideas can be applied to audio data.

---

## 10. Documentation and Release

- [ ] Keep README examples copy-pasteable.
- [ ] Document limitations honestly.
- [ ] Document supported PHP versions.
- [ ] Document GD requirements.
- [ ] Document the Morse file format.
- [ ] Add changelog entries for user-visible changes.
- [ ] Create a GitHub release after the PHP 8.5 upgrade is complete.
- [ ] Update Packagist metadata if necessary.

---

## Long-Term Direction

Image Morse Codec is an experimental project.

The long-term goal is to keep experimenting with unusual representations of digital data while maintaining a small, readable PHP implementation.

The project may eventually become a small family of related codecs and experiments involving images, audio, and other forms of digital data.