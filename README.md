
# 🎧 Audiovisualizer

**See what music looks like.**  
Audiovisualizer is a desktop app that generates colorful visual representations of music based on a unique mapping of audio frequencies (20 Hz–20,000 Hz) to visible light wavelengths (400–700 nm).

![Demo Screenshot](demo/screenshot.png)
![Dark Side of the Moon](demo/darkSideOfTheMoon.png)

---

## 🔍 What It Does

- 🔎 Accepts either:
  - ✅ An album name (auto-looked up)
  - ✅ A YouTube URL (downloads the audio)
- 🎼 Extracts frequency information from the audio using FFT
- 🌈 Maps frequencies to colors via a logarithmic scale:  
  `20 Hz → 700 nm (red)` … `20,000 Hz → 400 nm (violet)`
- 🖼️ Produces a unique visual "portrait" of the sound

---

## 🚀 Installation

# 🛠️ From Source (recommended)

```bash
git clone https://github.com/camnoval/audiovisualizer.git
cd audiovisualizer
pip install -r requirements.txt
python main.py
```
---

# Alternative (Downloadable Executable)

1. **Download the latest release on homepage**  
   👉 [Click here to download](https://camnoval.github.io/audiovisualizer/)  
   *(or clone the repo to run from source)*

2. **Run the app**  
   Just double-click the executable — no install required.

The downloadable executable is a self-contained package that includes all dependencies, so you can run it without needing to install Python or any libraries, but it takes up more space, takes longer to run, and may not work on all systems (not recommended).
---

## 📸 Examples

| Album | Visualization |
|-------|----------------|
| *Dark Side of the Moon* | ![](demo/darkSideOfTheMoon.png) |
| *Random Access Memories* | ![](demo/ram.png) |

---

## 🧠 How It Works

> The human ear hears from 20 Hz to 20,000 Hz.  
> The human eye sees light from 400 nm to 700 nm.  
> This app maps sound frequencies to wavelengths using a **logarithmic transformation** to simulate how we might “see sound.”

---

## 📊 Frequency to Wavelength Mapping

To convert sound frequency (Hz) into visible color (wavelength in nm), this app uses a **logarithmic scale** that reflects how both hearing and vision perceive information.

### 🔁 The Mapping Formula

We convert from frequency to wavelength with:

```
λ(f) = 700 - ((log10(f) - log10(20)) / (log10(20000) - log10(20))) * 300
```

This means:
- 🎵 `20 Hz` maps to **700 nm** → red
- 🎵 `20,000 Hz` maps to **400 nm** → violet
- The interpolation between them is smooth and logarithmic, just like human perception

This wavelength is then translated into an RGB value using a spectrum-based color mapping function.

## 📦 Features

- 🎵 YouTube audio support via `yt-dlp`
- 📁 Album lookup and batch processing
- 🎨 Logarithmic frequency-to-color mapping
- 📸 Save images of generated visuals

---

## 📌 Roadmap

- [ ] Add real-time visualization mode
- [ ] Export video/gif of animation
- [ ] Allow custom frequency → color mapping
- [ ] Website with demo and live visuals

---

## 🤝 Contributing

Pull requests are welcome! For major changes, please open an issue first.

---

## 📜 License

MIT License — see [`LICENSE`](LICENSE) for details.

---

## 🔗 Links

- 🔗 [Project Website](https://camnoval.github.io/audiovisualizer/)
- 🐙 [GitHub Repo](https://github.com/camnoval/audiovisualizer)

---

> Created with ❤️ by [@camnoval](https://github.com/camnoval)
