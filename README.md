# SoundBites - Audio Segmentation Tool

A browser-based audio segmentation tool that allows musicians and students to upload audio files, visualize waveforms, select time-based segments, and extract them as independent downloadable audio files.

## Features

- **Waveform Visualization**: Visual representation of audio with amplitude-based rendering
- **Interactive Region Selection**: Click and drag directly on the waveform to select time ranges
- **Audio Extraction**: Create unlimited clips from any portion of your audio
- **Multiple Export Formats**: Download clips as WAV (lossless) or MP3 (compressed)
- **Advanced Playback Controls**: Play, pause, stop, rewind/forward 5s, and region looping
- **Full Clip Controls**: Each extracted clip has independent playback controls
- **Keyboard Shortcuts**: Complete keyboard navigation for efficient workflow
- **Clip Management**: Rename, mute, and organize your extracted segments
- **No Installation Required**: Runs entirely in your browser

## Quick Start

1. **Open the Application**
   - Simply open `index.html` in a modern web browser
   - No installation, build process, or server required

2. **Upload Audio**
   - Click "Choose Audio File"
   - Select an audio file from your computer (MP3, WAV, OGG, FLAC, etc.)
   - Wait for the file to decode and the waveform to appear

3. **Select a Segment**
   - Click and drag on the master waveform to select a time range
   - Fine-tune the selection by dragging the region handles
   - Use playback controls to preview your selection

4. **Extract the Clip**
   - Click "Extract Selected Region"
   - A new clip appears below with its own mini-waveform

5. **Download Your Clip**
   - Rename the clip by editing the text field
   - Click "Download WAV" for lossless quality
   - Click "Download MP3" for smaller file size

## Browser Requirements

### Minimum Browser Versions

- **Chrome**: 66+
- **Firefox**: 61+
- **Safari**: 14.1+
- **Edge**: 79+

### Required Browser Features

- Web Audio API
- File API
- Blob/URL APIs
- Canvas API

All modern browsers support these features. If you're using an older browser, you'll see an error message on the page.

## Supported Audio Formats

The following audio formats are supported (depends on browser):

✅ **Widely Supported**
- MP3 (.mp3)
- WAV (.wav)
- OGG Vorbis (.ogg)
- AAC (.m4a, .aac)

⚠️ **Browser-Dependent**
- FLAC (.flac) - Chrome, Firefox, Edge
- WebM (.webm) - Chrome, Firefox, Edge
- AIFF (.aiff) - Safari

## Usage Guide

### Master Track Controls

**Playback Controls:**
- **Play/Pause**: Start or stop audio playback
- **Stop**: Stop playback and return to the beginning
- **⏪ -5s**: Rewind 5 seconds
- **⏩ +5s**: Forward 5 seconds

**Region Controls:**
- **Loop: Off/On**: Toggle continuous looping of the selected region (only enabled when region is selected)
- **Extract Selected Region**: Create a clip from the current selection (only enabled when region is selected)

### Selecting Regions

1. **Click and drag** on the master waveform to create a selection
2. A semi-transparent purple region appears showing your selection
3. **Resize** the region by dragging the edges/handles
4. **Move** the entire region by dragging in the middle
5. The "Loop" and "Extract Selected Region" buttons become enabled

### Loop Functionality

When you enable Loop:
- The selected region will play continuously
- Playback automatically jumps back to the start when it reaches the end
- Perfect for practicing specific sections of a song

### Creating Clips

1. Select a region on the master waveform (click and drag)
2. Click "Extract Selected Region" or press <kbd>E</kbd>
3. The clip appears in the "Extracted Clips" section below with its own waveform
4. The region is cleared, allowing you to select and extract another segment

### Managing Clips

Each extracted clip has **full independent controls**:

**Clip Information:**
- **Name Field**: Click to rename the clip (used for download filename)
- **Duration**: Displays the clip length

**Playback Controls:**
- **Play/Pause**: Toggle clip playback
- **Stop**: Stop and return to beginning
- **⏪ -5s**: Rewind 5 seconds
- **⏩ +5s**: Forward 5 seconds
- **Mute/Unmute**: Toggle audio on/off

**Export & Management:**
- **Download WAV**: Export as lossless WAV file
- **Download MP3**: Export as compressed MP3 file (128 kbps)
- **Delete**: Remove the clip (requires confirmation)

### Keyboard Shortcuts

**Master Track:**
- <kbd>Space</kbd> - Play/Pause
- <kbd>S</kbd> - Stop
- <kbd>←</kbd> (Left Arrow) - Rewind 5 seconds
- <kbd>→</kbd> (Right Arrow) - Forward 5 seconds
- <kbd>L</kbd> - Toggle Loop (when region selected)
- <kbd>E</kbd> - Extract Region (when region selected)

**Note:** Keyboard shortcuts work when not typing in text fields

### Tips & Tricks

- **Precise Selection**: The waveform cursor changes to a crosshair when you can drag to select
- **Multiple Clips**: Create as many clips as you need from the same source audio
- **Quick Navigation**: Use keyboard shortcuts for fast playback control
- **Region Resizing**: Drag the edges of the selection for precise timing
- **File Naming**: Clip names are automatically sanitized (special characters replaced with underscores)
- **Independent Playback**: Play multiple clips or the master track - each has its own timeline

## Export Formats

### WAV (Waveform Audio File Format)

- **Quality**: Lossless (identical to source)
- **File Size**: Larger (~10 MB per minute for stereo)
- **Best For**: Professional audio editing, archiving
- **Compatibility**: Universal support in all audio software

### MP3 (MPEG Audio Layer 3)

- **Quality**: 128 kbps (good quality)
- **File Size**: Smaller (~1 MB per minute)
- **Best For**: Sharing, mobile devices, casual listening
- **Compatibility**: Universal support in all devices and software

## Troubleshooting

### Can't Select a Region

- **Make sure audio is loaded**: The waveform must be fully loaded before you can select
- **Click and drag**: Press and hold the mouse button while dragging across the waveform
- **Look for the cursor**: The cursor should change to a crosshair when hovering over the waveform
- **Check console**: Press F12 to see if there are any error messages
- **Try refreshing**: Reload the page and upload the file again

### Loop Not Working

- **Select a region first**: Loop only works when a region is selected
- **Enable Loop**: Click the "Loop: Off" button to toggle it to "Loop: On"
- **Check playback**: The loop will start playing automatically when enabled
- **Region boundaries**: Make sure your region has clear start and end points

### Audio File Won't Load

- **Check Format**: Ensure your file is a supported audio format
- **Check Size**: Very large files (>100 MB) may take longer to decode
- **Try Another Browser**: Some formats are browser-specific
- **Check File**: Make sure the file isn't corrupted

### Waveform Doesn't Appear

- **Wait for Decoding**: Large files take time to process
- **Check Console**: Press F12 and look for error messages
- **Refresh Page**: Try reloading and uploading again

### Download Doesn't Start

- **Check Permissions**: Ensure browser allows downloads
- **Disable Pop-up Blocker**: May interfere with download
- **Check Filename**: Avoid very long clip names

### Performance Issues

- **Large Files**: Files over 100 MB may be slow
- **Many Clips**: Creating 50+ clips may slow down the browser
- **Close Other Tabs**: Free up browser memory
- **Use WAV Export**: MP3 encoding is more CPU-intensive

## Technical Details

### Architecture

- **Single-File Application**: Everything in one `index.html` file
- **No Build Process**: No npm, webpack, or compilation needed
- **No Backend**: Runs entirely in the browser
- **Dependencies**: Loaded via CDN (Wavesurfer.js, lamejs)

### Technologies Used

- **Web Audio API**: Native browser audio processing
- **Wavesurfer.js**: Waveform rendering and visualization
- **Regions Plugin**: Interactive time selection
- **lamejs**: MP3 encoding library
- **Canvas API**: Waveform drawing

### Audio Processing

- Audio is decoded into AudioBuffer format
- Clips are created by copying sample data for the selected time range
- WAV export uses manual PCM encoding
- MP3 export uses lamejs encoder at 128 kbps

## Privacy & Security

- **No Data Upload**: All processing happens in your browser
- **No Server Communication**: Your audio never leaves your computer
- **No Tracking**: No analytics or tracking code
- **Open Source**: Code is readable in the HTML file

## Use Cases

### For Musicians

- Extract guitar solos to practice along with
- Isolate drum patterns to learn
- Create backing tracks by extracting sections
- Analyze specific instrumental parts

### For Students

- Extract lecture segments for review
- Create study clips from long recordings
- Isolate examples from educational audio

### For Producers

- Quick audio segmentation for sampling
- Extract loops from full tracks
- Create reference clips for comparison

## Limitations

- Audio processing is limited by browser memory
- Very large files (>500 MB) may cause performance issues
- MP3 encoding is fixed at 128 kbps
- No batch processing or automation features
- No audio editing (volume, effects, etc.)

## Credits

- Built with [Wavesurfer.js](https://wavesurfer.xyz/)
- MP3 encoding by [lamejs](https://github.com/zhuker/lamejs)
- Uses Web Audio API and Canvas API

## License

MIT License - See LICENSE file for details

## Support

For issues or questions:
1. Check the Troubleshooting section above
2. Ensure your browser is up to date
3. Try a different browser to isolate the issue
4. Check browser console (F12) for error messages

---

**Version**: 1.1
**Last Updated**: December 2025

## Recent Updates (v1.1)

- ✅ Fixed region selection with drag functionality
- ✅ Fixed loop to properly loop selected regions without playing past the end
- ✅ Added full playback controls to extracted clips (Stop, Rewind, Forward)
- ✅ Added comprehensive keyboard shortcuts for efficient workflow
- ✅ Improved UI with visual instructions for region selection
- ✅ Enhanced clip management with independent playback controls
