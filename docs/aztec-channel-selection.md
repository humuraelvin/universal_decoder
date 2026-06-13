# Aztec Channel Selection

`Aztec Code/aztec_decode.py` extracts one image channel before resizing and binarizing the symbol.

## Parameters

- `image_path`: the image containing the Aztec code.
- `layers`: the Aztec layer count. The script uses this to calculate the target dimensions.
- `channel`: the image channel used for decoding. The default is `2`.

## Practical notes

Try another channel when the image has color artifacts or alpha transparency. A clean crop and the correct layer count are usually more important than aggressive preprocessing.
