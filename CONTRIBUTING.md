# Contributing

Contributions are welcome when they make the decoders easier to run, test, or reuse.

## Useful contribution areas

- Add a shared command-line interface for choosing a format and image path.
- Add per-format requirement files or a top-level `requirements.txt`.
- Add fixture images and tests for successful and failed decodes.
- Improve error messages for missing native dependencies such as ZBar or libdmtx.
- Return structured JSON from decoders so other applications can consume the output.

## Local workflow

1. Create a branch for your change.
2. Keep changes focused on one decoder or one documentation area.
3. Run the script you changed from its own directory.
4. Include before/after notes in the pull request.

## Style notes

- Keep paths and commands copy-pasteable on Linux/macOS shells.
- Mention Windows-specific setup only when a dependency needs it.
- Avoid committing generated annotated images unless they are intentional test fixtures.
