# Testing Plan

The project can gain confidence with small fixture-based tests.

## Test types

- Import tests for every decoder module.
- Smoke tests that decode known fixture images.
- Failure tests for missing files and non-matching images.
- Output-shape tests once JSON output is introduced.

## Fixture guidance

Use small images with known payloads and permissive licenses. Keep generated annotated images out of version control unless they are intentionally used as expected-output fixtures.

## Headless runs

Tests should not open OpenCV windows. Decoder functions can accept an option to disable preview windows, or tests can call lower-level decode helpers before visualization.
