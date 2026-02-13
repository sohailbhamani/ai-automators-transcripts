# Alex Finn Transcripts

Transcript archive of [Alex Finn (OpenClaw)](https://www.youtube.com/@AlexFinn) YouTube videos.

## Stats

- **Videos Downloaded**: 0 (bootstrap pending)
- **Date Range**: TBD
- **Last Updated**: Feb 2026

## Structure

```
alex-finn-transcripts/
├── README.md
├── index.json                    # Master index of all videos
├── video_ids.txt                 # All video IDs (one per line)
├── index/                        # Topic-based index
│   ├── README.md                 # All topics with episode counts
│   └── ...                       # Topic files
├── episodes/
│   └── YYYY-MM-DD-video-title/
│       └── transcript.md         # YAML frontmatter + full transcript
└── scripts/
    ├── download.py               # Download transcripts (youtube-transcript-api, free)
    ├── enrich.py                 # Entity extraction + classification
    ├── create_index.py           # Generate index.json
    └── build_index.py            # Build topic index files
```

## Transcript Format

Each `transcript.md` contains:

```yaml
---
title: "Video Title"
video_id: "abc123"
youtube_url: "https://www.youtube.com/watch?v=abc123"
publish_date: "2026-01-14"
duration: "32:18"
duration_seconds: 1938
view_count: 10000
author: "Alex Finn"

yt_tags:
  - "AI"
  - "Claude"

# AI-enriched metadata
content_type: "Tutorial"
primary_topic: "AI Tools"
difficulty: "Intermediate"
audience:
  - "Engineers"
entities:
  companies: []
  people: []
  products: []
  models: []
concepts: []
summary: []
---

# Video Title

[Full transcript text here]
```

## Usage

### Search transcripts
```bash
grep -r "Claude Code" episodes/
```

### Use index.json
```python
import json
with open('index.json') as f:
    data = json.load(f)
for video in data['videos']:
    print(f"{video['publish_date']}: {video['title']}")
```

## Credits

- Content by [Alex Finn](https://www.youtube.com/@AlexFinn)
- Transcripts via [youtube-transcript-api](https://github.com/jdepoix/youtube-transcript-api) (free)
- Metadata via YouTube Data API v3
