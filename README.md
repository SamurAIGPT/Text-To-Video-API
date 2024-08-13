# Text To Video API

### Youtube tutorial -> https://youtu.be/LDBnlO3PDBY

### Steps

To generate a video from text, here are the steps involved

1. Generate an API key from https://viral.vadoo.tv/profile
2. Setup a webhook url at https://viral.vadoo.tv/profile to received generated video metadata

### Python code

Install requests library to send a post request

```pip install requests```

Use the below code to generate a video, the download url of generated video will be sent to the webhook setup
Topic, voice, theme, language and duration are optional but can be customized. More info about these are available here https://docs.vadoo.tv/docs/category/guide

```
import requests

# Replace 'YOUR_API_KEY' with your actual API key
API_KEY = 'YOUR_API_KEY'
url = 'https://viralapi.vadoo.tv/api/generate_video'

# Define the request headers
headers = {
    'X-API-KEY': API_KEY,
    'Content-Type': 'application/json'
}

# Define the request body parameters
data = {
    'topic': 'Random AI Story',      # Optional: specify your topic or leave it as the default
    'voice': 'Charlie',              # Optional: specify the voice or leave it as the default
    'theme': 'Hormozi_1',            # Optional: specify the theme or leave it as the default
    'language': 'English',           # Optional: specify the language or leave it as the default
    'duration': '30-60'              # Optional: specify the duration or leave it as the default
}

# Make the POST request to generate the video
response = requests.post(url, headers=headers, json=data)

# Check if the request was successful
if response.status_code == 200:
    response_data = response.json()
    print(f"Video ID: {response_data['vid']}")
else:
    print(f"Failed to generate video. Status code: {response.status_code}")
    print(response.text)
```
