# Transcribe-and-Analyze-Meetings-or-Podcasts-with-Whisper-and-Google-Gemini-AI (n8n Workflow)

This project is an **automation workflow for n8n** that takes meeting or podcast recordings from your Gmail inbox, transcribes them using **OpenAI Whisper**, summarizes them with **Google Gemini AI**, and automatically shares a recap with all participants.  

It’s designed to save hours of manual transcription and note-taking, while ensuring key insights, decisions, and action items never get lost.  

---
 <img width="1822" height="838" alt="Screenshot 2025-09-25 133608" src="https://github.com/user-attachments/assets/f96f3b91-a58d-4ecf-aef3-b71cbdcbcef3" />

## ⚡ Features
- **Trigger on Gmail** → Detects new emails with audio/video attachments.  
- **File Management** → Uploads files to Google Drive, logs them in Google Sheets.  
- **Transcription** → Uses OpenAI Whisper to generate accurate transcripts.  
- **Summarization** → Uses Google Gemini AI to extract: 

  - Executive summary  
  - Key discussion points  
  - Decisions made  
  - Action items & next steps  
- **Collaboration** → Creates a Google Doc for each transcript and sends recap emails.  
- **Reliability** → Prevents duplicate processing by marking files as “DONE.”  

---

## 🚀 Getting Started

### 1. Import Workflow into n8n
- Clone or download this repository.  
- In n8n, open the workflow editor.  
- Click **⋯ → Import from File** and select the JSON file from this repo.  
- Alternatively, use **Import from URL** with the GitHub **raw JSON link**.  

---

### 2. Configure Credentials
This workflow uses the following external integrations:  
- **Gmail** → Trigger, fetch messages, send recap emails  
- **Google Drive** → Upload/share audio files  
- **Google Sheets** → Log audio files, track status  
- **Google Docs** → Store transcripts  
- **OpenAI Whisper** → Transcription  
- **Google Gemini (via LangChain)** → Summarization & analysis  

👉 You’ll need to set up credentials for each service in your n8n instance.  
> **Note:** Credentials are not included in the export for security reasons.  

---

### 3. Environment Variables
If your setup requires API keys or secrets, add them in your `.env` file or n8n environment settings:  
- `OPENAI_API_KEY` → For Whisper transcription  
- `GOOGLE_API_CREDENTIALS` → For Drive, Sheets, Docs, and Gmail  
- `GEMINI_API_KEY` → For Gemini AI  

---

### 4. Version Information
- Tested on **n8n v1.112.3**  
- Make sure your n8n instance is up to date to avoid node incompatibility.  

---

### 5. Custom Nodes or Dependencies
This workflow uses standard n8n nodes **plus LangChain integration**.  
If you plan to extend it:  
- Install any required community nodes via n8n’s package manager.  
- Update node parameters if versions differ.  

---

## 📝 Usage
1. Import the workflow JSON.  
2. Configure your credentials.  
3. Update node parameters (e.g., Google Drive folder ID, Sheet ID).  
4. Activate the workflow.  
5. Send yourself a test email with an audio attachment (mp3, wav, m4a, mp4, mov).  

If successful:  
- The audio file will be uploaded & logged.  
- A transcript will be created in Google Docs.  
- Gemini will generate a summary.  
- Participants will receive a recap email.  
- The entry will be marked **DONE** in Google Sheets.  

---

## 🛠️ Troubleshooting
- **Workflow doesn’t trigger?**  
  - Check Gmail credentials & trigger settings.  
- **File not uploaded?**  
  - Verify Google Drive folder permissions.  
- **No transcript generated?**  
  - Check OpenAI Whisper API key & usage limits.  
- **Gemini errors?**  
  - Make sure API key is valid and quota isn’t exceeded.  
- **Duplicate processing?**  
  - Ensure “DONE” column is being updated in Google Sheets.  

---

## 🤝 Contributing
Pull requests and suggestions are welcome! If you build improvements (e.g., multi-language support, Slack/Teams integration), please share them back with the community.  

---

## 📄 License
This project is released under the MIT License.  

