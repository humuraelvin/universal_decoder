# Windows Setup Notes

The decoders can run on Windows, but native barcode libraries need extra attention.

## Python environment

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install opencv-python pyzbar pillow imageio numpy pylibdmtx pyztec
```

## Native dependencies

- `pyzbar` needs the ZBar runtime available on the system path.
- `pylibdmtx` needs the libdmtx runtime available on the system path.
- PDF417 requires Docker Desktop if you use the existing ZXing container workflow.

If a script imports correctly but detects nothing, first verify the sample image path, then confirm the native runtime can be loaded by Python.
