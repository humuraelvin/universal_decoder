# Supported Formats

This document summarizes what each decoder is currently designed to handle and what to check when a scan fails.

## QR Code

- Script: `QR Code/qr_code_decoder.py`
- Engine: `pyzbar`
- Best for: URLs, Wi-Fi strings, contact data, text payloads, and images containing multiple QR codes.
- Output: decoded data, symbol type, position, size, content category, and an annotated image.

Troubleshooting:

- Make sure all three finder patterns are visible.
- Use a clear image with strong contrast.
- Avoid motion blur and heavy perspective distortion.

## Linear barcodes

- Script: `Barcode/barcode_decoder.py`
- Engine: `pyzbar`
- Best for: EAN, UPC, Code 128, Code 39, and other barcode types supported by ZBar.
- Output: barcode type, decoded payload, bounding box, and EAN-13 field breakdown when applicable.

Troubleshooting:

- Keep the bars sharp and horizontal where possible.
- Increase image resolution if the bars are too thin.
- Improve lighting to reduce glare.

## Data Matrix

- Script: `Data Matrix Code/data_matrix_docde.py`
- Engine: `pylibdmtx`
- Best for: compact industrial and manufacturing labels.
- Output: decoded data, location, size, and annotated image.

Troubleshooting:

- Install the native libdmtx dependency for your operating system.
- Crop closer to the code if the image contains many distracting patterns.
- Increase contrast before decoding.

## MaxiCode

- Script: `Maxicode/decode_maxicode.py`
- Engine: `pyzbar`
- Best for: logistics and shipping labels, especially UPS-style symbols.
- Output: decoded data, symbol type, bounding box, and annotated image.

Troubleshooting:

- Make sure the center bullseye is visible.
- Use enough resolution to preserve the hexagonal modules.
- Avoid images where labels are bent or folded.

## Aztec Code

- Script: `Aztec Code/aztec_decode.py`
- Engine: `pyztec`
- Best for: compact Aztec symbols where the layer count is known.
- Output: decoded payload returned from `process_and_decode`.

Troubleshooting:

- Set the correct `layers` value before running the script.
- Try another channel when the symbol is embedded in an image with alpha or color channels.
- Use a clean crop around the symbol.

## PDF417

- Script: `pdf-417/decode_pdf-417.py`
- Engine: ZXing Java libraries executed in an OpenJDK Docker container.
- Best for: stacked barcodes on IDs, forms, labels, and transport documents.
- Output: ZXing decode output plus an annotated polygon when point data is returned.

Troubleshooting:

- Start Docker before running the script.
- Run the command from the `pdf-417/` directory so the JAR paths resolve.
- Check that `image.png` exists or update `barcode_image` in the script.
