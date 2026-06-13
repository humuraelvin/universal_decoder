# Dependency Map

| Decoder | Python packages | Native/runtime dependency |
| --- | --- | --- |
| QR Code | `opencv-python`, `pyzbar` | ZBar |
| Linear barcode | `opencv-python`, `pyzbar` | ZBar |
| Data Matrix | `pillow`, `opencv-python`, `pylibdmtx` | libdmtx |
| MaxiCode | `opencv-python`, `pyzbar` | ZBar with MaxiCode support |
| Aztec | `imageio`, `numpy`, `pillow`, `pyztec` | None beyond Python wheels in most setups |
| PDF417 | `opencv-python`, `numpy` | Docker plus OpenJDK image, ZXing JARs |

Keep dependency installation close to the decoder you are testing. This makes it easier to isolate native-library problems from image-quality problems.
