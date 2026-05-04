# SAM-Audio Benchmark

This repository collects static pages and supporting materials for inspecting and analyzing SAM-Audio benchmark examples.

## Available Pages

### SAM-Audio Benchmark Viewer

Interactive benchmark browser for reviewing videos, text prompts, span prompts, visual mask previews, target metadata, source datasets, and paper evaluation subset tags.

- Viewer page: https://TerryShenty.github.io/SAM-Audio-Benchmark/sam-audio-benchmark-viewer/
- Documentation: [sam-audio-benchmark-viewer/README.md](sam-audio-benchmark-viewer/README.md)

## Repository Structure

```text
.
├── README.md
└── sam-audio-benchmark-viewer/
    ├── index.html
    ├── README.md
    ├── masks/
    └── media/
```

## Local Preview

To preview the repository locally:

```bash
cd /path/to/SAM-Audio-Benchmark
python3 -m http.server 8000
```

Then open:

```text
http://localhost:8000/sam-audio-benchmark-viewer/
```

## Attribution

SAM-Audio is developed by Meta AI. This repository is an independent visualization and inspection resource, not the official SAM-Audio repository.

Official SAM-Audio repository:

https://github.com/facebookresearch/sam-audio
