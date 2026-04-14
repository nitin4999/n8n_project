# 📧 YouTube Creator Email Finder

> Automated pipeline to find YouTube creator contact emails using **n8n + Apify + OpenAI GPT-4o Mini**

---

## 🚀 What This Does

This workflow automates the entire process of finding YouTube creator emails for outreach and partnerships.

**Flow:**
1. You enter a search term (e.g. "BGMI gameplay Hindi")
2. Apify scrapes matching YouTube channels
3. Each channel's description is extracted
4. GPT-4o Mini reads the description and pulls out any email addresses (even hidden ones like `name(at)gmail(dot)com`)
5. You get a clean list of emails — ready for outreach

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| n8n | Workflow automation engine |
| Apify (streamers/youtube-scraper) | Search YouTube by keyword |
| Apify (apidojo/youtube-scraper) | Scrape individual channel details |
| OpenAI GPT-4o Mini | Extract emails from channel descriptions |

---

## ⚙️ Setup Instructions

### 1. OpenAI API Key
- Go to [platform.openai.com/api-keys](https://platform.openai.com/api-keys)
- Create an API key
- Add billing at [OpenAI Billing](https://platform.openai.com/settings/organization/billing/overview)
- Add the key as **OpenAI credentials** in n8n

### 2. Apify API Key
- Sign up at [console.apify.com](https://console.apify.com/)
- Get your token from [Apify Integrations](https://console.apify.com/account/integrations)
- In n8n, create a **HTTP Query Auth** credential:
  - Key: `token`
  - Value: `YOUR_APIFY_API_KEY`
- Attach this credential to both HTTP Request nodes: `Search YouTube` and `Scrape Channels`

### 3. Import Workflow
- Open your n8n instance
- Click **Import** → upload the `.json` file from this repo
- Connect your credentials
- Hit **Execute**

---

## 📝 How to Use

1. Open the workflow in n8n
2. Edit the **"Set Search Term"** node:
   - `Search` → your YouTube keyword (e.g. `"tech review Hindi"`)
   - `channels` → number of channels to scan
3. Click **Execute Workflow**
4. Emails will appear in the output of the **AI Agent** node

---

## 📁 Project Structure

```
├── workflow.json        # n8n workflow file (import this)
└── README.md
```

---

## 💡 Use Cases

- Finding gaming/tech/lifestyle YouTubers for brand deals
- Building influencer outreach lists
- Automating creator research for agencies

---

## ⚠️ Disclaimer

This tool is for legitimate outreach purposes only. Always respect creators' privacy and follow YouTube's Terms of Service.

---

## 👤 Author

**Nitin Kumar** — AI Automation Developer  
📧 nitingaur72817@gmail.com  
🌐 [Portfolio](https://my-portfolio-1-psi-three.vercel.app/)
