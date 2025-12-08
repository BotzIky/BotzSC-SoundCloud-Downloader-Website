# SoundCloud Downloader - Download SoundCloud Music as MP3

A fast, responsive, and easy-to-use SoundCloud downloader web application that allows you to search SoundCloud tracks and download them as MP3 in high quality.

---

## 🌟 Features

- **Search by Title** – Find tracks using song title, artist name, or keywords
- **Full Track Metadata** – Display title, artist, duration, play count, likes, release date, and thumbnail
- **Download by URL** – Paste a direct SoundCloud track URL and download its audio
- **High Quality MP3** – Download audio as MP3 from SoundCloud tracks
- **In-Browser Preview** – Play audio directly in the browser before downloading
- **Unified Experience** – Title search and URL download work together as one seamless flow
- **Fully Responsive** – Optimized for desktop, tablet, and mobile devices
- **Dark Theme UI** – Beautiful dark mode interface with smooth, modern layout
- **No Registration Required** – Completely free to use without any signup

---

## 🚀 Demo

```text
https://soundcloud.botzaku.eu.org
```

---

## 📸 Screenshots

![Screenshot](https://cdn.botzaku.eu.org/1-hqrOxLOymxRHQNpdbZROryxHNx0YOph)

### Desktop View

- Clean and modern interface
- Two-in-one search and URL download
- Track list with metadata and thumbnails
- Current track preview and download options

### Mobile View

- Fully responsive layout
- Touch-friendly buttons and controls
- Hamburger menu navigation
- Optimized list and cards for small screens

---

## 🛠️ Technologies Used

- **HTML5** – Semantic markup
- **CSS3** – Modern styling with flexbox and grid
- **JavaScript (ES6+)** – Async/await, Fetch API
- **Bootstrap Icons** – Icon library
- **SweetAlert2** – Beautiful alert notifications
- **BotzApi** – Backend API for SoundCloud content fetching

---

## 📋 API Integration

This application uses the BotzApi SoundCloud endpoints:

### 1. Search by Title

```http
GET https://host.optikl.ink/soundcloud/search?query={QUERY}
```

#### Example Response

```json
[
  {
    "id": 2091968745,
    "title": "Denny Caknan - Sigar",
    "url": "https://soundcloud.com/andy-setyaputra/denny-caknan-sigar",
    "duration": "6:36",
    "thumbnail": "https://i1.sndcdn.com/artworks-EZHa4sCo66aXFFa2-3SHT2Q-large.png",
    "author": {
      "name": "Andy Setyaputra",
      "url": "https://soundcloud.com/andy-setyaputra"
    },
    "like_count": "778",
    "download_count": "0",
    "play_count": "101.9K",
    "release_date": "2025-05-08"
  }
]
```

The app will:

- Render a list of tracks
- Show thumbnail, title, artist, duration, stats, and release date
- Provide a **Download** button on each result
- When clicked, the selected track’s URL is passed to the download API

---

### 2. Download by URL

```http
GET https://host.optikl.ink/soundcloud/download?url={SOUNDCLOUD_URL}
```

#### Example Response

```json
{
  "title": "SIGAR [ Cookies Minor Ft. Emil Zhee ] APITA GROUP - Preview 2024",
  "author": "Cookies Minor IV # MINORITY SQUAD !!!",
  "audio_url": "https://cf-media.sndcdn.com/8683Fqs17cIg.128.mp3?...",
  "duration": "233 sec",
  "thumbnail": "https://i1.sndcdn.com/artworks-LtEy7yqYWZ43x4PM-D9zaTw-large.jpg"
}
```

The app will:

- Show current track info (title, author, duration, thumbnail, original URL)
- Update the page title dynamically to match the track
- Provide buttons to:
  - **Download MP3** (main button)
  - **Open in SoundCloud**
  - **Download MP3** (secondary option in the Download Options section)
  - **Play in Browser** via `<audio>` element

---

## 🎯 How to Use

1. **Search by Title**

   - Enter song title, artist, or keyword in the **Search by Title** field  
   - Click **Search**  
   - Browse the result list with metadata and thumbnails  
   - Click **Download** on the track you want  
   - The URL will be used to fetch the MP3 and show the download panel

2. **Download by URL**

   - Copy a SoundCloud track URL (e.g. `https://soundcloud.com/artist/track`)  
   - Paste it into the **Download by URL** field  
   - Click **Download**  
   - The app will fetch metadata and the audio file  

3. **Choose Download Option**

   - Click **Download MP3** to save the audio file  
   - Or use the built-in **Play in browser** audio player to preview the track  

4. **Download Another Track**

   - Click **Download Another** to reset the interface  
   - Repeat the process for more tracks

---

## 💻 Installation

### Local Development

1. Clone the repository:

```bash
git clone https://github.com/yourusername/BotzSC-SoundCloud-Downloader-Website.git
cd BotzSC-SoundCloud-Downloader-Website
```

2. Open `index.html` in your browser (recommended via local server):

```bash
# Using Python
python -m http.server 8000

# Using Node.js
npx http-server

# Or simply open the file directly
open index.html
```

3. Navigate to:

```text
http://localhost:8000
```

in your browser.

---

### Deploy to GitHub Pages

1. Push your code to GitHub repository  
2. Go to **Settings > Pages**  
3. Select branch `main` and folder `/ (root)`  
4. Click **Save**  
5. Your site will be live at:

```text
https://yourusername.github.io/BotzSC-SoundCloud-Downloader-Website
```

(Adjust repository name as needed.)

---

### Deploy to Vercel

```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
vercel
```

---

### Deploy to Netlify

1. Drag and drop your project folder to Netlify  
2. Or connect your GitHub repository  
3. Deploy automatically with default settings  

---

## 🔧 Configuration

### Change API Endpoints

In `index.html`, edit the SoundCloud API URLs in the JavaScript section:

```javascript
// Search by title
const searchUrl =
  'https://host.optikl.ink/soundcloud/search?query=' +
  encodeURIComponent(query);

// Download by URL
const downloadUrl =
  'https://host.optikl.ink/soundcloud/download?url=' +
  encodeURIComponent(url);
```

Change `https://host.optikl.ink` to your own API host if needed.

---

### Customize Colors

Edit colors directly in the CSS section of `index.html`:

```css
/* Primary accent - green */
--primary-color: #98ff98;

/* Secondary accent */
--secondary-color: #7ae87a;

/* Background */
--bg-color: #000;

/* Text */
--text-color: #f1fdf1;
```

Or update the corresponding hard-coded color values (`#98ff98`, `#7ae87a`, etc.).

---

## 📱 Browser Support

- ✅ Chrome (latest)  
- ✅ Firefox (latest)  
- ✅ Safari (latest)  
- ✅ Edge (latest)  
- ✅ Opera (latest)  
- ✅ Mobile browsers (iOS Safari, Chrome Mobile, Samsung Internet)

---

## ⚠️ Legal Disclaimer

This tool is provided for **personal use only**. Please ensure you have the rights to download and use any audio content.

- Do not use downloaded content for commercial purposes without permission  
- Always credit the original artist/creator  
- Respect intellectual property rights and SoundCloud’s terms of service  

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository  
2. Create your feature branch:

```bash
git checkout -b feature/AmazingFeature
```

3. Commit your changes:

```bash
git commit -m "Add some AmazingFeature"
```

4. Push to the branch:

```bash
git push origin feature/AmazingFeature
```

5. Open a Pull Request

---

## 🐛 Bug Reports

If you find any bugs, please create an issue on GitHub with:

- Description of the bug  
- Steps to reproduce  
- Expected behavior  
- Screenshots (if applicable)  
- Browser and OS information  

---

## 📄 License

This project is licensed under the MIT License – see the [LICENSE](LICENSE) file for details.

---

## 👨‍💻 Author

**BotzAku (Riski Yanda)**

- Website: <https://botzaku.eu.org>  
- Instagram: [@botzaku](https://instagram.com/botzaku)  
- TikTok: [@botzaku](https://tiktok.com/@botzaku)  
- Twitter: [@botz_aku](https://twitter.com/botz_aku)  
- Telegram: [BotzAku](https://t.me/BotzAku)  
- WhatsApp: [Channel](https://whatsapp.com/channel/0029VbBjxQl8qIzmg51J5W3x)  
- Discord: [Server](https://discord.gg/Ehr7DrsU)

---

## 🙏 Acknowledgments

- [Bootstrap Icons](https://icons.getbootstrap.com/) for beautiful icons  
- [SweetAlert2](https://sweetalert2.github.io/) for elegant alerts  
- All contributors and users of this project  

---

## ❗ Important

If you want to disable ads, remove the last `<script>` tags at the bottom of `index.html` that are used for ad loading.

---

## ⭐ Star History

If you find this project useful, please consider giving it a star on GitHub!

---

Made with ❤️ by [BotzAku](https://botzaku.eu.org)

**Disclaimer**: This is an unofficial tool and is not affiliated with SoundCloud.
