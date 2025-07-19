# Whisper ASR

OpenAI Whisper ASR (Automatic Speech Recognition) web service that provides high-quality speech-to-text transcription capabilities using CPU processing only. This service is based on OpenAI's Whisper model and offers a simple REST API for audio transcription without requiring GPU hardware.

## Features

- **High-Quality Transcription**: Uses OpenAI's state-of-the-art Whisper model for accurate speech recognition
- **CPU Processing**: Runs entirely on CPU - no GPU required
- **Multiple Model Sizes**: Supports different Whisper model sizes (tiny, base, small, medium, large)
- **Fast Processing**: Uses faster_whisper engine for optimized CPU performance
- **REST API**: Simple HTTP API for easy integration with other applications
- **Multiple Audio Formats**: Supports various audio file formats (WAV, MP3, M4A, etc.)
- **Language Detection**: Automatic language detection and multilingual support
- **Timestamps**: Optional word-level and segment-level timestamps
- **Cross-Platform**: Supports both ARM64 and AMD64 architectures

## Configuration

This instance is configured with:

- **Model**: `small` - Good balance between speed and accuracy
- **Engine**: `faster_whisper` - Optimized for CPU performance
- **Processing**: CPU-only (no GPU requirements)

## API Usage

The service provides a REST API accessible at port 9000. You can transcribe audio files by sending POST requests to the `/asr` endpoint.

### Example API Call

```bash
curl -X POST -F "audio_file=@your_audio.wav" http://your-server:9000/asr
```

### Response Format

```json
{
  "text": "Your transcribed text here",
  "segments": [
    {
      "start": 0.0,
      "end": 2.5,
      "text": "Your transcribed text here"
    }
  ]
}
```

## Supported Audio Formats

- WAV
- MP3
- M4A
- FLAC
- OGG
- And many more formats supported by FFmpeg

## Use Cases

- **Podcast Transcription**: Convert audio podcasts to text
- **Meeting Notes**: Transcribe recorded meetings and calls
- **Content Creation**: Generate subtitles for videos
- **Accessibility**: Create text versions of audio content
- **Voice Assistants**: Process voice commands and queries
- **Research**: Analyze spoken content and interviews

## Performance Considerations

- **CPU Usage**: This version uses CPU processing, which is slower than GPU but doesn't require special hardware
- **Memory**: Requires sufficient RAM for model loading (approximately 2GB for the small model)
- **Processing Time**: Transcription will be slower compared to the GPU version but still efficient
- **Compatibility**: Works on any system without GPU requirements

## Model Information

The `small` model provides:

- **Size**: ~244 MB
- **Speed**: Moderate transcription speed on CPU
- **Accuracy**: Good for most use cases
- **Languages**: Supports 99 languages
- **Memory**: ~2GB RAM usage

## CPU vs GPU Version

- **CPU Version**: No special hardware requirements, works on any system, slower processing
- **GPU Version**: Requires NVIDIA GPU, much faster processing, higher hardware requirements

For more information about the Whisper ASR web service, visit the [official repository](https://github.com/ahmetoner/whisper-asr-webservice).
