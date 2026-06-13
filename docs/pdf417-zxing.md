# PDF417 ZXing Workflow

The PDF417 script uses ZXing through Java because Python PDF417 support is less consistent than QR or linear barcode decoding.

## How it works

1. The script checks for the ZXing JAR files and `image.png`.
2. Docker starts an `openjdk:17` container.
3. The current folder is mounted into `/app`.
4. ZXing decodes the image and prints result metadata.
5. OpenCV draws a polygon when point data is available.

## Common fixes

- Start Docker before running the script.
- Run the script from the `pdf-417/` folder.
- Keep the ZXing JAR files beside the script unless you update the paths.
- Replace `image.png` or change `barcode_image` to point at your sample.
