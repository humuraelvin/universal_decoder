# CLI Roadmap

A shared command-line interface would make the decoders easier to use outside of one-off experiments.

## Proposed command

```bash
universal-decoder --format qr --image ./samples/qr.png --json
```

## Useful options

- `--format`: `qr`, `barcode`, `datamatrix`, `maxicode`, `aztec`, or `pdf417`.
- `--image`: path to the input image.
- `--json`: return machine-readable output.
- `--annotate`: write an annotated image when bounding boxes are available.
- `--no-preview`: skip OpenCV GUI windows for headless environments.

## Implementation approach

Keep each decoder module focused, then add a small dispatcher that validates arguments and normalizes result output.
