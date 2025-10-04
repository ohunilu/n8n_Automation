# 🎨 Generate AI Book Covers with Google Gemini & Send via Email

This workflow allows users to generate **AI-powered book cover designs instantly** using Google Gemini, consolidate them into download links, and deliver them directly to an author’s inbox. The entire process is triggered by a simple **n8n form** that collects book details, including title, subtitle, author, genre, preferred colors, and style.

It automates the cover design process, ensuring **fast, affordable, and professional-quality results** for self-publishers, freelancers, and indie authors.

---

## 💡 Benefits of this workflow

- **Full Automation**: From prompt creation to email delivery — the workflow runs hands-free once set up.
- **AI-Powered Creativity**: Uses **Google Gemini** to adapt designs dynamically based on title, genre, style, and mood.
- **Instant Delivery**: Sends download links for both covers to the user’s email inbox.
- **Cost & Time Savings**: Skip the high cost per professional design and generate covers in under 2 minutes.
- **Quick Deployment**: ~2-3 hours per cover
- **Productivity Boost**: Focus on writing, not design hassle
- **Secure**: Uses API-based credentials for Gemini and Gmail to ensure safe communication.

---

## ⚙️ How It Works

- **Trigger**: n8n Form collects inputs via a secure channel
- **Validate**: Ensures required fields are clean and assigned values
- **Generate**: A precrafted prompt with validated details is sent to Gemini to generate image
- **Upload**: Generated images are uploaded to Google Drive
- **Consolidate**: Uploaded image URLs and metadata packed together
- **Send**: Gmail sends links to inputed emaill address
- **Notify**: A meesage with links is sent to admins chatbot

---

## 🛠 Setup in 5 Steps

1. **Sign up** for [n8n Cloud](https://n8n.io)
2. **Add Credentials**
   - Google Gemini API key (from Google Cloud Console)
   - Gmail App Password (if 2FA enabled)
3. **Create Form** fields: `title`, `subtitle`, `author`, `genre`, `style`, `colors[]`, `email`
4. **Import Workflow JSON** or configure nodes manually
5. **Test & Deploy** → share your form link, and let the covers roll in

---

## ⚠️ Limitations

- _LLM Cost:_ Google Gemini API incurs per-image costs (~$0.04 each)
- _Temporayr Binary Data:_ n8n’s binary download links may expire or need authentication
- _Basic form validation:_ only (complex rules require extra logic)
- _Restriction on Links:_ Some email clients may block external links

---

## 📌 Version

- **v1.0**: Initial release (Form → Gemini → Gmail)
- **v1.1**: Fixed email delivery with consolidated URLs

---

## ☎️ Need Help Setting Up Or Customization?

- **Email**: [Send Mail](info@electronicexchange.ng)
- **LinkedIn**: [![LinkedIn](https://img.shields.io/badge/LinkedIn-%230077B5.svg?logo=linkedin&logoColor=white)](https://linkedin.com/in/ohunilu)
- **Twitter(X)**: [![X](https://img.shields.io/badge/X-black.svg?logo=X&logoColor=white)](https://x.com/ohunilu)
- **Youtube**: [![YouTube](https://img.shields.io/badge/YouTube-%23FF0000.svg?logo=YouTube&logoColor=white)](https://youtube.com/@ohunilu)
- **Discord**: [![Discord](https://img.shields.io/badge/Discord-%237289DA.svg?logo=discord&logoColor=white)](https://discord.gg/ohunilu)

---

✨ _Automate. Analyze. Amplify._ ✨
