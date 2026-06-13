# Universal Decoder

Universal Decoder is a collection of focused Python decoders for common barcode and 2D code formats used in robotics, logistics, inventory, and document-processing workflows.

The repository keeps each format in its own folder so experiments stay small and easy to run. Most scripts read a sample image, decode the symbol, print the decoded payload, and write or display an annotated result.

## Supported decoders

| Folder | Format | Main script | Notes |
| --- | --- | --- | --- |
| `QR Code/` | QR Code | `qr_code_decoder.py` | Uses `pyzbar` and OpenCV for one or more QR codes in an image. |
| `Barcode/` | Linear barcodes | `barcode_decoder.py` | Uses `pyzbar` and includes EAN-13 structure output. |
| `Data Matrix Code/` | Data Matrix | `data_matrix_docde.py` | Uses `pylibdmtx` with PIL and OpenCV visualization. |
| `Maxicode/` | MaxiCode | `decode_maxicode.py` | Uses `pyzbar` with MaxiCode-specific symbol filtering. |
| `Aztec Code/` | Aztec | `aztec_decode.py` | Uses `pyztec`, Pillow, ImageIO, and NumPy. |
| `pdf-417/` | PDF417 | `decode_pdf-417.py` | Uses ZXing Java libraries through Docker/OpenJDK and annotates detected points with OpenCV. |

## Quick start

Clone the repository and install the Python packages used by the scripts you plan to run:

```bash
git clone https://github.com/humuraelvin/universal_decoder.git
cd universal_decoder
python -m venv .venv
source .venv/bin/activate
pip install opencv-python pyzbar pillow imageio numpy pylibdmtx pyztec
```

Some libraries also need native system packages. For example, `pyzbar` needs ZBar, `pylibdmtx` needs libdmtx, and the PDF417 workflow expects Docker so it can run the OpenJDK container.

## Running a decoder

Each folder contains a sample script and image. Run a script from its own folder so relative paths resolve correctly:

```bash
cd "QR Code"
python qr_code_decoder.py
```

For PDF417:

```bash
cd pdf-417
python decode_pdf-417.py
```

The PDF417 script uses the checked-in ZXing JAR files and mounts the current directory into an OpenJDK Docker container.

## Output

Depending on the format, scripts print decoded data, symbol type, pixel position, dimensions, and useful metadata such as EAN-13 structure or QR content category. Several scripts also save annotated image files showing the detected symbol area.

## Good use cases

- Robotics perception experiments that need to read codes from camera frames.
- Inventory and package-tracking prototypes.
- Document-processing labs that compare barcode formats.
- Coursework demos for computer vision and applied decoding.

## Next improvements

- Add a shared CLI entry point that accepts an image path and format.
- Add a `requirements.txt` split by decoder family.
- Add automated tests with small fixture images.
- Normalize output into JSON for downstream applications.
