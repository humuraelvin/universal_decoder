# pyzbar Workflows

The QR, linear barcode, and MaxiCode scripts use `pyzbar` with OpenCV images.

## Strengths

- Simple Python API.
- Supports several common 1D and 2D formats through ZBar.
- Returns decoded data plus rectangle and polygon metadata.

## Practical flow

1. Load the image with OpenCV.
2. Call `decode` with all symbols or a format-specific symbol list.
3. Decode the byte payload to text.
4. Draw rectangles or polygons for review.
5. Save the annotated image.

## When to specialize

Use a symbol filter when the image may contain multiple symbol types and you only want one family, such as QR Code or MaxiCode.
