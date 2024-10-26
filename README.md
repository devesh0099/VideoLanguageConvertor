
# VoxLingua: AI-Powered Video Language Translator

VoxLingua is an basic video translation system that converts videos from one language to another while preserving the original speaker's voice characteristics. The project uses state-of-the-art AI models for speech recognition, translation, and voice synthesis.

## 🌟 Features

- **Audio Extraction**: Automatically extracts audio from video files
- **Speech Recognition**: Uses OpenAI's Whisper model for accurate speech-to-text conversion
- **Neural Translation**: Employs Facebook's M2M100 model for high-quality translations
- **Voice Cloning**: Maintains the original speaker's voice characteristics in the translated audio
- **Seamless Integration**: Automatically combines translated audio with the original video
- **Support for Multiple Languages**: Currently supports English to Hindi translation (extensible to other languages)

## ❗ Known Limitations

While VoxLingua provides many advanced features, it is still a basic model with the following limitations:

1. **No Lip Sync**: Translated audio is not synced with the lip movements in the video, which may impact realism.
2. **Voice Clarity**: The synthesized voice may lack some clarity, especially for complex tonal languages or in background noise.
3. **Audio Sync**: The translated audio may occasionally fall out of sync with the video, especially in longer clips.
4. **Normal Pace Only**: Currently only supports normal speech pace, which may sound unnatural for slower or faster speech.
5. **Single Voice**: Cannot handle multiple speakers within a single video; limited to one voice for translation.
6. **Limited Length**: Only supports videos up to 2 minutes, making it unsuitable for longer content.

## 📺 Example

- **Link to Original Video**: [Video](https://www.youtube.com/watch?v=aO1-6X_f74M)
- **Translated Video**: ![example](Example.mp4)

## 🛠️ Technical Architecture

1. **Video Processing**
   - Extracts audio from input video using `moviepy`
   - Converts video to WAV format for processing

2. **Speech Recognition**
   - Uses `whisper-large-v3` model for accurate transcription
   - Splits transcript into sentence-level chunks for better translation

3. **Translation**
   - Utilizes Facebook's M2M100 (418M parameter model)
   - Performs sentence-by-sentence translation for accuracy

4. **Voice Synthesis**
   - Implements XTTS v2 model for voice cloning
   - Preserves original voice characteristics in translated audio

5. **Video Generation**
   - Merges translated audio with original video
   - Maintains original video quality and synchronization

## 🔧 Installation

```bash
pip install accelerate
pip install sentencepiece
pip install transformers
pip install spacy-transformers
pip install TTS
pip install pydub
pip install moviepy
pip install joblib
```

## 💻 Usage

1. Place your input video in the project directory as `video.mp4`
2. Run the notebook cells in sequence
3. The final translated video will be saved as `final_video.mp4`

## 🔍 Requirements

- Python 3.7+
- CUDA-compatible GPU (recommended)
- Sufficient disk space for temporary files
- Internet connection for model downloads

## ⚠️ Resource Management

The project includes functionality to save intermediate results to disk, allowing for session restarts when dealing with limited computational resources. This is particularly useful when processing longer videos.

## 🚀 Future Improvements

- Support for additional language pairs
- Custom voice model training
- Batch processing of multiple videos
- Real-time translation capabilities
- Web interface for easier usage
- Support for additional video codecs

## 📝 License

This project is open-source and available under the GPL-3.0 License.

## 🙏 Acknowledgments

- OpenAI for the Whisper ASR model
- Facebook for the M2M100 translation model
- Coqui TTS team for the XTTS voice synthesis model
- MoviePy contributors
