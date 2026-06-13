# Native Library Notes

Some Python packages wrap native barcode libraries. A successful `pip install` does not always mean the native runtime is available.

## ZBar

Used by `pyzbar` for QR, linear barcode, and MaxiCode decoding. Install the operating-system ZBar package when imports fail or no symbols are detected despite clear input.

## libdmtx

Used by `pylibdmtx` for Data Matrix decoding. Install the operating-system libdmtx package when the Python package cannot load its backend.

## Docker and OpenJDK

Used by the PDF417 workflow. Docker keeps Java setup isolated, but it must be installed and running before the script executes.

## Review checklist

- Confirm the Python package imports successfully.
- Confirm the native library can be loaded by the wrapper package.
- Run the decoder from its own folder so local sample paths resolve.
- Save annotated output for visual inspection when a decode fails.
