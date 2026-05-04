# SAM-Audio Benchmark Viewer

An interactive static viewer for inspecting the SAM-Audio benchmark examples used in my experiments. The viewer is designed to make the benchmark easier to browse, compare, and audit before running or interpreting audio separation results.

Live site:

https://TerryShenty.github.io/SAM-Audio-Benchmark/sam-audio-benchmark-viewer/

## What This Viewer Shows

This viewer presents a curated SAM-Audio benchmark table with video, prompt, mask, and metadata for each example. It is intended as a lightweight inspection tool rather than a model inference demo.

Each benchmark card includes:

- The source video or YouTube preview.
- The text prompt used for SAM-Audio.
- The temporal span prompt, when available.
- The target sound category or target node.
- Extra dataset metadata, such as source labels, target visibility, loudness, and overlap information.
- Visual mask previews for examples with visual prompts.
- Paper evaluation subset tags, such as text-only, text+span, and visual-only settings.

## How To Use It

Open the GitHub Pages site:

https://TerryShenty.github.io/SAM-Audio-Benchmark/sam-audio-benchmark-viewer/

Use the filters at the top of the page to narrow the benchmark:

- **Task**: filter by benchmark task, such as instrument separation, speech cleaning, speaker separation, or general sound separation.
- **Paper Eval Subset**: filter by the evaluation split or prompting setup used in the SAM-Audio paper.
- **Source Dataset**: filter by the original dataset source.
- **Search**: search by description, video ID, target node, task, or dataset fields.

Click **Load preview** on a YouTube-like example to load the embedded video preview. Non-YouTube examples use local video previews when available.

For examples with masks, the mask strip below the video shows sampled binary mask previews. These masks indicate the visual object or region associated with the target sound.

## Interpreting A Card

Each card contains three main parts:

1. **Media panel**

   Shows the video preview, video ID, clip time range, duration, whether a visual mask is available, and mask previews.

2. **Prompt panel**

   Shows the text prompt and span prompt. The text prompt is the natural-language condition used to query SAM-Audio. The span prompt gives the time interval where the target sound is active, when available.

3. **Metadata panel**

   Shows the target node, scene labels, target visibility, target loudness, overlap information, and the paper evaluation subsets associated with the example.

## Why This Viewer Is Useful

The benchmark contains many cases where the prompt, video, and mask need to be checked together. For example, some speaker separation examples are ambiguous when using text only, because multiple people may speak in the same clip. Visual masks and span prompts can clarify which object or speaker is intended.

This viewer helps with:

- Inspecting whether the benchmark prompt matches the visible or audible content.
- Checking whether a visual mask is available and whether it appears reasonable.
- Comparing text-only, span, and visual prompting settings.
- Finding difficult cases, such as overlapping speakers, ambiguous targets, or multiple same-class sound sources.
- Preparing qualitative analysis before listening to SAM-Audio outputs.

## Notes About YouTube Previews

Some examples are YouTube-like clips embedded through YouTube. Whether they play inside the page depends on YouTube availability, browser settings, login status, and regional restrictions.

If a YouTube iframe asks for login or fails to play, this is a YouTube embedding limitation rather than a problem with the benchmark metadata.

## Repository Structure

```text
.
├── index.html      # Static benchmark viewer
├── masks/          # Sampled visual mask preview images
└── media/          # Local video previews for non-YouTube examples
```

The site is fully static and can be hosted with GitHub Pages.

## Local Preview

To preview the site locally:

```bash
cd /path/to/SAM-Audio-Benchmark
python3 -m http.server 8000
```

Then open:

```text
http://localhost:8000/sam-audio-benchmark-viewer/
```

## Data And Attribution

This viewer is built for inspecting SAM-Audio benchmark examples and related prompt metadata. SAM-Audio is developed by Meta AI. This repository is an independent visualization/inspection page and is not the official SAM-Audio repository.

Official SAM-Audio repository:

https://github.com/facebookresearch/sam-audio

