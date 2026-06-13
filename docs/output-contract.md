# Output Contract Ideas

The current scripts print human-readable summaries. A future shared CLI can expose a consistent JSON shape for downstream tools.

```json
{
  "format": "qr-code",
  "source": "image.png",
  "results": [
    {
      "type": "QRCODE",
      "data": "https://example.com",
      "bounds": { "x": 10, "y": 20, "width": 200, "height": 200 },
      "points": [[10, 20], [210, 20], [210, 220], [10, 220]]
    }
  ]
}
```

A stable output contract would make the project easier to use from robotics pipelines, web APIs, and batch-processing jobs.
