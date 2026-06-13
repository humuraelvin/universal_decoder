# Sample Image Conventions

Each decoder folder currently keeps a sample image near the script. That is convenient for manual experiments, but the naming should stay predictable.

## Suggested naming

- `sample.png` for the primary positive fixture.
- `sample-rotated.png` for rotation tests.
- `sample-low-contrast.png` for preprocessing experiments.
- `negative.png` for an image that should not decode.

## Metadata

When adding fixtures, include the expected decoded payload in documentation or a future fixture manifest. That makes automated tests easier to write and review.
