# YouTube Downloader

A secure, user-friendly desktop application for downloading YouTube videos and converting them to MP3 audio format. Built with PyQt5 and powered by yt-dlp (formerly youtube-dl), this tool provides a privacy-focused alternative to web-based downloaders.

## 🎵 Overview

The YouTube Downloader is a lightweight GUI application that allows users to download YouTube videos and automatically convert them to high-quality MP3 files. Designed as a privacy-conscious alternative to browser-based download services, the application runs entirely on your local machine without requiring internet access to third-party websites.

The application features a clean, intuitive interface with real-time download progress tracking, making it easy for users to download their favorite music and audio content for offline listening.

## ✨ Features

- **Video to MP3 Conversion**: Automatic conversion of YouTube videos to MP3 format
- **High-Quality Audio**: Downloads best available audio quality for optimal sound
- **Progress Tracking**: Real-time download progress bar with percentage completion
- **Custom Save Location**: Choose where to save downloaded files
- **Privacy-Focused**: No web trackers, ads, or third-party data collection
- **Offline Operation**: Works entirely on your local machine
- **Simple Interface**: Clean, easy-to-use GUI built with PyQt5
- **Error Handling**: Comprehensive error handling for failed downloads

## 🛠️ Technology Stack

- **GUI Framework**: PyQt5
- **Download Engine**: yt-dlp (modern fork of youtube-dl)
- **Audio Processing**: FFmpeg (integrated with yt-dlp)
- **Python Version**: 3.6+
- **Platform**: Cross-platform (Windows, macOS, Linux)

## 📋 Prerequisites

- **Python**: Version 3.6 or higher
- **PyQt5**: GUI framework for the application
- **yt-dlp**: Modern YouTube downloader and extractor
- **FFmpeg**: Required for audio conversion (usually included with yt-dlp)
- **Operating System**: Windows 7+, macOS 10.12+, or Linux

### System Requirements
- **RAM**: Minimum 512MB (1GB recommended)
- **Storage**: 50MB for application + space for downloaded files
- **Network**: Stable internet connection for downloads

## 🚀 Installation & Setup

### 1. Install Python Dependencies
```bash
# Install PyQt5
pip install PyQt5

# Install yt-dlp
pip install yt-dlp

# Install additional dependencies (if needed)
pip install youtube-dl  # Alternative/fallback option
```

### 2. Download FFmpeg (Required for audio conversion)
```bash
# Windows (using Chocolatey)
choco install ffmpeg

# macOS (using Homebrew)
brew install ffmpeg

# Ubuntu/Debian
sudo apt install ffmpeg

# Or download from https://ffmpeg.org/download.html
```

### 3. Run the Application
```bash
python abc.py
```

## 🎮 Usage

### Basic Operation
1. **Launch the Application**: Run `python abc.py`
2. **Enter YouTube URL**: Paste the YouTube video URL in the "YouTube URL" field
3. **Set Save Location**: Specify where you want to save the MP3 file
4. **Start Download**: Click the "Download" button
5. **Monitor Progress**: Watch the progress bar update in real-time
6. **Access File**: Find your MP3 file in the specified save location

### Interface Guide
- **YouTube URL Field**: Input field for YouTube video URLs
- **Save Path Field**: Directory path where MP3 files will be saved
- **Progress Bar**: Visual indicator of download progress (0-100%)
- **Download Button**: Initiates the download and conversion process
- **Exit Button**: Closes the application

### Supported URL Formats
- Standard YouTube videos: `https://www.youtube.com/watch?v=VIDEO_ID`
- YouTube Music: `https://music.youtube.com/watch?v=VIDEO_ID`
- YouTube Shorts: `https://www.youtube.com/shorts/VIDEO_ID`
- Playlist items (individual videos only)

## 🏗️ Project Structure

```
YouTube-Downloader/
├── abc.py                 # Main application file (PyQt5 GUI)
├── untitled.ui           # Qt Designer UI file
├── README.md             # Project documentation
└── requirements.txt      # Python dependencies (if present)
```

## 🔧 Technical Details

### Download Process
1. **URL Validation**: Verify YouTube URL format and accessibility
2. **Metadata Extraction**: Retrieve video title, duration, and available formats
3. **Audio Extraction**: Download best available audio stream
4. **Format Conversion**: Convert audio to MP3 using FFmpeg
5. **File Saving**: Save MP3 file to specified location

### Audio Quality Settings
- **Format**: MP3 (MPEG-1 Audio Layer III)
- **Quality**: Best available audio stream
- **Codec**: AAC/MP3 conversion via FFmpeg
- **Sample Rate**: Original video sample rate (usually 44.1kHz or 48kHz)

### File Naming Convention
Files are saved with the format: `youtube-{video_id}-{title}.mp3`

Example: `youtube-dQw4w9WgXcQ-Rick Astley - Never Gonna Give You Up.mp3`

## ⚙️ Configuration

### yt-dlp Options (Configured in Code)
```python
ydl_opts = {
    'outtmpl': 'path/%(extractor)s-%(id)s-%(title)s.mp3',
    'format': 'bestaudio/best',
    'extractaudio': True,
    'audioformat': 'mp3',
    'progress_hooks': [progress_callback],
    'noplaylist': True
}
```

### Customization Options
- **Output Template**: Modify file naming format
- **Audio Quality**: Adjust format selection
- **Progress Hooks**: Customize progress reporting
- **Additional Options**: Add FFmpeg parameters for audio processing

## 🔒 Privacy & Security

### Privacy Features
- **Local Processing**: All downloads happen on your machine
- **No Data Collection**: No tracking, analytics, or user data sent to servers
- **No Browser Extensions**: Avoids browser-based download risks
- **Clean Code**: Transparent, auditable source code

### Security Considerations
- **Trusted Dependencies**: Uses well-maintained yt-dlp library
- **Input Validation**: Basic URL validation to prevent malicious input
- **Local File Access**: Only accesses specified save directories
- **No Network Uploads**: Downloaded files remain on local machine

## 🚨 Legal & Ethical Considerations

### Usage Guidelines
- **Personal Use**: Intended for personal, non-commercial use only
- **Copyright Compliance**: Respect copyright laws and content creator rights
- **Terms of Service**: Adhere to YouTube's Terms of Service
- **Fair Use**: Only download content you have legal rights to access

### Important Notes
- This tool is for educational and personal use
- Commercial distribution of downloaded content may violate copyright laws
- Always respect content creators and platform policies
- Use responsibly and ethically

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Suggested Improvements
- Add support for multiple video formats (MP4, WebM)
- Implement playlist download functionality
- Add batch download capabilities
- Include metadata tagging for MP3 files
- Enhance error handling and user feedback

## 📄 License

This project is developed as part of an academic assignment. Please refer to your institution's guidelines for usage and distribution.

## 🐛 Troubleshooting

### Common Issues
- **"Command not found"**: Ensure yt-dlp and FFmpeg are installed
- **Download fails**: Check internet connection and YouTube URL validity
- **Audio conversion error**: Verify FFmpeg installation
- **Permission denied**: Ensure write access to save directory

### Debug Mode
Enable verbose output by modifying the yt-dlp options in the code:
```python
ydl_opts['verbose'] = True
```

## 📚 References

- [yt-dlp Documentation](https://github.com/yt-dlp/yt-dlp)
- [PyQt5 Documentation](https://pypi.org/project/PyQt5/)
- [FFmpeg Documentation](https://ffmpeg.org/documentation.html)
- [YouTube Terms of Service](https://www.youtube.com/t/terms)

---

**Built with ❤️ for secure, private YouTube audio downloads**
