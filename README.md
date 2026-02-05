# Text To Video API

[![GitHub stars](https://img.shields.io/github/stars/SamurAIGPT/Text-To-Video-API?style=social)](https://github.com/SamurAIGPT/Text-To-Video-API/stargazers)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Python](https://img.shields.io/badge/python-3.7+-blue.svg)](https://www.python.org/downloads/)

Generate AI videos from text with a simple API call. Create engaging short-form content for TikTok, YouTube Shorts, Instagram Reels, and more.

## Tutorials

- **YouTube**: [Watch Tutorial](https://youtu.be/LDBnlO3PDBY)
- **Medium**: [Read Article](https://medium.com/@anilmatcha/text-to-video-api-in-python-ai-video-automation-tutorial-561b49241d70)

## Features

- **Text-to-Video** - Generate complete videos from text prompts
- **Customizable Voice** - Choose from multiple AI voices
- **Multiple Themes** - Apply different visual styles
- **Language Support** - Generate videos in multiple languages
- **Duration Control** - Specify video length (30-60s, etc.)
- **Webhook Delivery** - Receive video URL when generation completes

## Quick Start

### 1. Get API Key

Sign up and get your API key at [viral.vadoo.tv/profile](https://viral.vadoo.tv/profile)

### 2. Set Up Webhook

Configure your webhook URL at [viral.vadoo.tv/profile](https://viral.vadoo.tv/profile) to receive generated video metadata.

### 3. Generate Video

```bash
pip install requests
```

```python
import requests

API_KEY = 'YOUR_API_KEY'
url = 'https://viralapi.vadoo.tv/api/generate_video'

headers = {
    'X-API-KEY': API_KEY,
    'Content-Type': 'application/json'
}

data = {
    'topic': 'Random AI Story',      # Your video topic
    'voice': 'Charlie',              # Voice selection
    'theme': 'Hormozi_1',            # Visual theme
    'language': 'English',           # Output language
    'duration': '30-60'              # Video duration
}

response = requests.post(url, headers=headers, json=data)

if response.status_code == 200:
    print(f"Video ID: {response.json()['vid']}")
else:
    print(f"Error: {response.status_code}")
```

## API Reference

### Endpoint

```
POST https://viralapi.vadoo.tv/api/generate_video
```

### Headers

| Header | Value |
|--------|-------|
| `X-API-KEY` | Your API key |
| `Content-Type` | `application/json` |

### Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `topic` | string | No | Video topic/subject |
| `voice` | string | No | AI voice to use |
| `theme` | string | No | Visual theme |
| `language` | string | No | Output language |
| `duration` | string | No | Video duration |

### Response

```json
{
  "vid": "video_id_here"
}
```

The download URL will be sent to your configured webhook.

## Available Options

See full documentation for all available voices, themes, and languages: [docs.vadoo.tv](https://docs.vadoo.tv/docs/category/guide)

## Use Cases

- **Social Media Content** - TikTok, YouTube Shorts, Instagram Reels
- **Marketing Videos** - Product demos, explainers
- **Educational Content** - Tutorials, how-tos
- **Entertainment** - Stories, facts, trivia

## Web App

Prefer a no-code solution? Use the web app: [Text to Video API](https://www.vadoo.tv/text-to-video-api)

## Follow for Updates

- [Anil Chandra Naidu Matcha](https://twitter.com/matchaman11)
- [Ankur Singh](https://twitter.com/ankur_maker)

## Related Projects

- [Text-To-Video-AI](https://github.com/SamurAIGPT/Text-To-Video-AI) - Self-hosted text-to-video
- [AI-Youtube-Shorts-Generator](https://github.com/SamurAIGPT/AI-Youtube-Shorts-Generator) - Generate YouTube Shorts

## License

MIT License - see [LICENSE](LICENSE) for details.
