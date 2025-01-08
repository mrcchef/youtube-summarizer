
# YouTube Video Summarizer API

A FastAPI-based service that generates concise summaries of YouTube videos using their transcripts and AI language models.

## Features

- Extract transcripts from YouTube videos
- Support for multiple languages
- Generate AI-powered summaries using Gemini 2.0
- RESTful API interface

## Prerequisites

- Python 3.7+
- FastAPI
- OpenAI Python client
- youtube_transcript_api

## Installation

1. Clone the repository:
```bash
git clone https://github.com/mrcchef/youtube-summarizer.git
cd youtube-summarizer-api
```

2. Install the required dependencies:
```bash
pip install fastapi uvicorn openai youtube_transcript_api
```

3. Set up your OpenRouter API key:
   - Sign up at [OpenRouter](https://openrouter.ai/)
   - Get your API key
   - Replace the `OPENROUTER_API_KEY` in the code with your key

## Usage

1. Start the server:
```bash
python main.py
```

2. The API will be available at `http://localhost:8000`

3. Make a POST request to `/summarize` endpoint:
```json
{
    "video_id": "VSvGZq2FeOU",
    "language_code": "hi"
}
```

Example using curl:
```bash
curl -X POST "http://localhost:8000/summarize" \
     -H "Content-Type: application/json" \
     -d '{"video_id": "VSvGZq2FeOU", "language_code": "hi"}'
```

## API Endpoints

### POST /summarize

Generates a summary of a YouTube video.

#### Request Body

| Field         | Type   | Description                                    | Default |
|---------------|--------|------------------------------------------------|---------|
| video_id      | string | YouTube video ID                               | -       |
| language_code | string | Language code for the transcript (e.g., "en")  | "en"    |

#### Response

```json
{
    "summary": "Generated summary of the video content"
}
```

## Error Handling

The API includes error handling for:
- Invalid YouTube video IDs
- Unavailable transcripts
- Language support issues
- API rate limiting
- General server errors

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## Acknowledgments

- [FastAPI](https://fastapi.tiangolo.com/)
- [YouTube Transcript API](https://github.com/jdepoix/youtube-transcript-api)
- [OpenRouter](https://openrouter.ai/)
```
