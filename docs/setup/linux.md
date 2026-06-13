# Linux Setup Notes

These steps cover a typical Ubuntu or Debian-based environment for the Python decoders.

## Base packages

```bash
sudo apt update
sudo apt install python3 python3-venv python3-pip libzbar0 libdmtx0b docker.io
```

`libzbar0` is needed by `pyzbar`. `libdmtx0b` is needed by `pylibdmtx`. Docker is only required for the PDF417 workflow, which runs ZXing inside an OpenJDK container.

## Python environment

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install --upgrade pip
pip install opencv-python pyzbar pillow imageio numpy pylibdmtx pyztec
```

Run each decoder from its own folder so sample-image paths and generated output paths stay predictable.
