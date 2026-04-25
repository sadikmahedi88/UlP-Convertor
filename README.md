📘 Murphy ULP Processor v1.0

Advanced ULP / Combo File Processor – Extract, clean, sort by country, and send reports to Telegram.

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=26&duration=3000&pause=500&color=39FF14&center=true&vCenter=true&width=600&lines=Murphy+ULP+Processor;Extract+%26+Sort+Credentials;Auto+Country+Detection;Telegram+Reports" alt="Typing SVG" />
</p>

---

✨ Features

Feature Description
🧠 Smart Extraction Handles multiple delimiters (:, ;, \|) and long / malformed lines.
🗺️ Country Sorting Detects country codes from Netflix patterns (netflix.com/eg, netflix.com:us) and creates separate folders per country.
📧 Automatic Classification Splits email:pass (contains @) from user:pass (no @) into separate files.
📊 Detailed Stats Total lines, valid combos, duplicates, bad lines, password strength analysis (numeric/alpha/mixed), average length.
🤖 Telegram Reports Sends an HTML summary + a ZIP archive of all results (up to 50 MB). Includes clickable channel & chat links.
🎨 Rich Console UI Live progress bars, coloured tables, panels – works on Termux, Linux, Windows.
⚡ Batch Mode Process an entire folder of .txt files in one go.
🔁 Deduplication Ensures no duplicate combos are saved.

---

📦 Installation

```bash
git clone https://github.com/yourusername/murphy-ulp-processor.git
cd murphy-ulp-processor
pip install -r requirements.txt
```

requirements.txt (create it if missing):

```
rich
requests
iso3166
colorama
```

💡 All libraries are lightweight and work on Termux, Linux, Windows, and macOS.

---

🚀 Usage

```bash
python murphy_ulp.py
```

Interactive workflow

1. Select input source – choose a single .txt file, a folder (batch mode), or pick from the list of files in the current directory.
2. Enter keyword – used for filtering and naming output folders (e.g., TikTok, Netflix).
3. Optional domain filter – only keep lines containing this string (e.g., gmail.com).
4. Telegram setup – provide your bot token and chat ID (optional – if skipped, results are saved locally only).
5. Processing – watch live progress, deduplication, and country detection.
6. Results – all combos are saved in {keyword}_results/, then zipped and sent to Telegram (if configured).

---

📁 Output Structure

```
{keyword}_results/
├── {keyword}_all.txt                # Every valid combo
├── {keyword}_email_pass.txt         # Only lines with @ in the username
├── {keyword}_user_pass.txt          # Lines without @
└── Countries/
    ├── Egypt/
    │   └── Egypt_hits.txt
    ├── United States/
    │   └── United States_hits.txt
    └── ... (other detected countries)
```

🔍 Country detection is triggered when a line contains netflix.com/eg, netflix.com:us, etc. – exactly as in the original Netflix Hunter tool.

---

🤖 Telegram Integration

What is sent Format Limit
HTML Summary Report Text with bold, code blocks, and clickable links Unlimited
ZIP archive All result files compressed ≤ 50 MB (Telegram limit)

How to get your bot token & chat ID

1. Bot token – talk to @BotFather, create a bot, copy the token.
2. Chat ID – talk to @userinfobot, it will reply with your ID.

---

📊 Example Summary (Telegram)

```
╔══════════════════════════════════════════════════════════════╗
║           MURPHY ULP PROCESSOR - FINAL REPORT               ║
╚══════════════════════════════════════════════════════════════╝

🔍 Keyword: Netflix

📊 PERFORMANCE METRICS:
• Total lines processed: 125,430
• Valid combos: 8,234
• Duplicates skipped: 1,204
• Bad combos: 1,002
• Filtered out: 38

📧 EXTRACTION TYPES:
• Email:pass found: 6,450
• User:pass found: 1,784

⏱️ TIME: 12m 34s

🔐 PASSWORD ANALYSIS:
• Numeric only: 1,234 (15.0%)
• Alpha only: 2,345 (28.5%)
• Mixed (strong): 4,655 (56.5%)
• Average length: 12

🌐 COUNTRIES DETECTED (4):
• Egypt (EG): 3,210 combos
• United States (US): 1,800 combos
• Saudi Arabia (SA): 950 combos
• United Arab Emirates (AE): 210 combos

📁 OUTPUT FILES (15 files):
• Netflix_all.txt
• Netflix_email_pass.txt
• Netflix_user_pass.txt
• Countries/ folder

💎 Developer: @pypkg
📢 Channel: https://t.me/+zZUKD1RHroA5ODc8
💬 Chat: https://t.me/pyabrodies
```

---

🛠️ Requirements

· Python 3.8+
· Internet connection (for Telegram uploads, optional)
· No tkinter – pure terminal application.

---

👤 Developer & Contact

· Developer: @pypkg
· Channel: https://t.me/+zZUKD1RHroA5ODc8
· Chat / Support: https://t.me/pyabrodies

⚡ For issues, feature requests, or contributions, open an issue on GitHub or contact via Telegram.

---

📜 License

MIT – free to use, modify, and distribute with proper attribution.

---

<p align="center">
  Made with ❤️ by <b>@pypkg</b> – <i>Murphy ULP Processor v2.0</i>
</p>
```

---
