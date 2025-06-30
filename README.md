# SnapSync 🎬

An AI-powered Flask web app that transforms your uploaded images and text into short, narrated vertical video reels using ElevenLabs (text-to-speech) and FFmpeg (video generation).

## 🔧 Features

- Upload multiple images and a description.
- Converts text into AI-generated voice narration using ElevenLabs API.
- Uses FFmpeg to create a vertical 1080x1920 video reel from your inputs.
- Automatically runs in the background to detect and convert new uploads.
- View all generated reels in a public gallery.

---

## 🧠 Tech Stack

- **Flask** – Backend web framework  
- **ElevenLabs API** – For generating voiceover from text  
- **FFmpeg** – For video creation from images and audio  
- **Python (threading, subprocess, os)** – Core logic  
- **HTML/CSS (Jinja templates)** – Frontend (basic UI)  

---

## 🗂️ File Structure

```bash
snapsync/
├── user_uploads/           # Stores uploaded images, text, and audio
│   └── .gitkeep
├── static/
│   ├── reels/              # Stores generated videos
│   │   └── .gitkeep
│   └── songs/              # (optional) background songs if added
├── templates/
│   ├── index.html
│   ├── create.html
│   └── gallery.html
├── main.py                 # Flask app logic
├── generate_process.py     # Background reel generator
├── text_to_audio.py        # ElevenLabs text-to-speech handler
├── .env.example            # Sample environment file
├── .gitignore              # Ignored files
├── done.txt                # Tracks completed conversions
└── README.md               # Project documentation
```

---

## ⚙️ Setup Instructions

1. **Clone the project**

```bash
git clone <repo-url>
cd snapsync
```

2. **Install dependencies**

```bash
pip install flask python-dotenv elevenlabs
```

3. **Install FFmpeg**  
Make sure FFmpeg is installed and added to your system path.  
👉 [FFmpeg Download](https://ffmpeg.org/download.html)

4. **Set up `.env` file**

Create a `.env` file in the root directory:

```
ELEVENLABS_API_KEY=your_elevenlabs_api_key
```

5. **Start the Flask server**

```bash
python main.py
```

6. **Start the background processor**

In a separate terminal:

```bash
python generate_process.py
```

---

## 🖼️ How It Works

1. Visit the home page and upload images + enter your description.
2. The backend:
   - Saves the files.
   - Converts text → speech (audio.mp3).
   - Uses FFmpeg to combine images + audio → vertical reel.
3. The final video appears in the **Gallery** tab!

---

## ✅ Example Output

```
🖼️ Input: 3 images + "Nature is beautiful and soothing"
🎧 Output: Narrated voice using ElevenLabs
🎬 Final Video: 1080x1920 MP4 in /static/reels/
```

---

## ✍️ Author  
Namrata Tamboli

---

## 📜 License

This project is open-source and free to use for educational and demo purposes.
