# The AI Automators Transcripts

YouTube channel: @theaiautomators (https://youtube.com/@theaiautomators)

The AI Automators - Building AI agents, automation workflows, and n8n integrations.

## Stats

- **16 videos** (Nov 2025 - Mar 2026)
- Synced daily at 12:00 UTC

## Structure

- `episodes/` - Raw transcript files with YAML frontmatter
- `index/` - Processed searchable index by topic
- `index.json` - Full video metadata index
- `scripts/` - Sync and processing scripts

## Sync Schedule

GitHub Actions runs daily at 12:00 UTC to sync latest transcripts.

## Usage

```bash
pip install -r requirements.txt
export SUPADATA_API_KEY=your_key
export YOUTUBE_API_KEY=your_key
python scripts/discover.py
python scripts/download.py
python scripts/enrich.py
python scripts/create_index.py
python scripts/build_index.py
```
