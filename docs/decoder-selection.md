# Decoder Selection Guide

Use the visual pattern and use case to choose the right script.

| Use case | Likely format | Decoder folder |
| --- | --- | --- |
| Website links, Wi-Fi setup, contact cards | QR Code | `QR Code/` |
| Retail products and inventory labels | EAN, UPC, Code 128, Code 39 | `Barcode/` |
| Small industrial part labels | Data Matrix | `Data Matrix Code/` |
| UPS and logistics labels | MaxiCode | `Maxicode/` |
| Compact transport or ticket symbols | Aztec | `Aztec Code/` |
| IDs, forms, stacked label data | PDF417 | `pdf-417/` |

If a symbol type is unknown, start with the universal barcode decoder and then move to the format-specific decoder when more control is needed.
