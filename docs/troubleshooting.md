# Troubleshooting

## Image not found

Most scripts use a hard-coded sample image name. Run the command from the decoder folder or update the image path in the script.

## Decoder imports fail

Check native libraries first:

- `pyzbar` requires ZBar.
- `pylibdmtx` requires libdmtx.
- PDF417 requires Docker to run the OpenJDK container.

## No symbol detected

Try these checks before changing code:

1. Crop closer to the symbol.
2. Increase image resolution.
3. Improve contrast and lighting.
4. Rotate the image so the symbol is easier for the decoder to locate.
5. Confirm that the chosen decoder matches the symbol type.

## GUI window does not open

OpenCV preview windows require a desktop session. On headless servers, comment out `cv2.imshow`, `cv2.waitKey`, and `cv2.destroyAllWindows`, then rely on the saved annotated image.
