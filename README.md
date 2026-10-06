# 🤖 Daily AI & Technology Intelligence Report

An automated AI-powered technology intelligence workflow built with **n8n**.

This project automatically collects recent AI and technology news from multiple RSS sources, processes and cleans the collected data, analyzes the articles using an LLM through OpenRouter, generates a structured intelligence report, and delivers the final report through email.

---

## 🎯 Project Overview

Keeping up with the rapidly changing AI and technology ecosystem can be time-consuming.

This automation solves that problem by creating a daily technology intelligence pipeline that:

- Collects recent technology and AI news
- Combines articles from multiple sources
- Cleans and deduplicates the data
- Sorts articles by publication date
- Uses AI to analyze the collected information
- Generates an executive-friendly report
- Highlights the 5 most important stories
- Provides key takeaways
- Sends the final report by email

The workflow is designed to run automatically every day.

---

## ✨ Features

- ⏰ Automated scheduled execution
- 📰 Multi-source RSS news collection
- 🔗 RSS article aggregation
- 🧹 Article data cleaning
- ♻️ Duplicate article detection
- 📅 Publication-date sorting
- 🤖 LLM-powered news analysis
- 📊 Structured technology intelligence report
- ⭐ Top 5 Highlights
- 💡 Key Takeaways
- 🏷️ Technology category classification
- 📧 Automated email delivery
- 🐳 Docker-based local n8n deployment

---

## 🔄 Workflow Architecture

```text
                    ┌── RSS Feed 1 ──┐
                    ├── RSS Feed 2 ──┤
                    ├── RSS Feed 3 ──┤
                    ├── RSS Feed 4 ──┤
Schedule Trigger ───┼── RSS Feed 5 ──┤
                    ├── RSS Feed 6 ──┤
                    ├── RSS Feed 7 ──┤
                    ├── RSS Feed 8 ──┤
                    ├── RSS Feed 9 ──┤
                    └── RSS Feed 10 ─┘
                              │
                              ▼
                            Merge
                              │
                              ▼
                            Limit
                              │
                              ▼
                    JavaScript Processing
                              │
                              ▼
                       Basic LLM Chain
                              │
                              ▼
                     OpenRouter Chat Model
                              │
                              ▼
                        Send an Email
⚙️ Workflow Process
1. Schedule Trigger

The workflow starts automatically according to the configured schedule.

The automation is configured to run daily.

2. RSS News Collection

The workflow collects recent articles from multiple AI and technology RSS sources.

3. Merge

Articles from the different RSS feeds are combined into a single stream.

4. Limit

The workflow controls the number of articles passed to the processing stage.

5. JavaScript Processing

The JavaScript processing node:

Extracts article titles
Extracts descriptions
Extracts URLs
Extracts publication dates
Extracts source information
Removes duplicate articles
Sorts articles by publication date
6. AI Analysis

The processed articles are passed to an LLM through OpenRouter.

The AI analyzes the supplied articles and generates a structured report containing:

Executive Summary
Top 5 Highlights
Detailed News Stories
Category
Status
Why It Matters
Key Takeaways

The AI is instructed to use only information supplied by the collected articles and avoid inventing facts or URLs.

7. Email Delivery

The generated HTML report is automatically sent through email.

📰 RSS Sources

The workflow currently collects information from multiple technology-focused sources, including:

Google News – AI Tools
Google News – AI Research
9to5Google
Android Authority
Android Police
How-To Geek
MakeUseOf
TechCrunch
XDA Developers
AlternativeTo
🧠 AI Report Structure

The generated report contains:

Executive Summary

A concise overview of the most important themes in the collected news.

Top 5 Highlights

The five most important stories selected from the detailed report.

News Stories

Detailed summaries of the collected technology news.

Each story includes:

Summary
Why It Matters
Category
Status
Source
Key Takeaways

Five concise insights derived from the collected stories.

🛠️ Technology Stack
Technology	Purpose
n8n	Workflow automation
Docker	Local containerized deployment
RSS	News collection
JavaScript	Data cleaning, deduplication and sorting
OpenRouter	LLM access
Generative AI / LLM	News analysis and report generation
SMTP	Email delivery
📸 Screenshots
Workflow Overview

Workflow Execution

AI Processing

Final Report

📄 Sample Report

A sample generated report is available here:

View Sample Report

🎥 Demo

A demonstration video showing the workflow is available here:

View Demo Video

🚀 Installation & Setup
Prerequisites

Before running the project, install:

Docker
n8n
OpenRouter account/API access
SMTP/email account
Run n8n with Docker
docker run -it --rm --name n8n -p 5678:5678 -v n8n_data:/home/node/.n8n docker.n8n.io/n8nio/n8n

Open n8n in your browser:

http://localhost:5678
Import the Workflow
Open n8n.
Import workflow.json.
Configure the OpenRouter credential.
Configure the SMTP credential.
Configure your sender and recipient email.
Check the workflow settings and schedule.
Execute the workflow manually for testing.
Activate the workflow for scheduled execution.
🔐 Security

Credentials should be configured inside n8n and should never be committed to GitHub.

Do not publish:

API keys
Passwords
Access tokens
SMTP credentials
Private credentials
Personal account information

The workflow JSON included in this repository is intended to be safe for portfolio demonstration and requires credentials to be configured separately.

📁 Project Structure
daily-ai-technology-intelligence-n8n/
│
├── README.md
├── workflow.json
├── sample-report.md
│
├── screenshots/
│   ├── workflow-overview.png
│   ├── workflow-execution.png
│   ├── ai-processing.png
│   └── final-report.png
│
└── demo/
    └── demo-video-link.txt
🔮 Future Improvements

Planned improvements include:

Expand the number of intelligence categories
Add more reliable technology news sources
Add AI tool discovery
Store historical reports
Add database-based historical deduplication
Add Telegram notifications
Add Notion integration
Add analytics dashboard
Add trend detection
Add source reliability scoring
Add automated weekly and monthly summaries
🎓 Skills Demonstrated

This project demonstrates practical experience with:

Workflow Automation
n8n
Generative AI
LLM Integration
RSS Data Processing
JavaScript
Data Cleaning
Data Deduplication
Prompt Engineering
OpenRouter
SMTP
Docker
API/Credential Management
Automated Reporting
👨‍💻 Author

Jay Suthar

B.Tech Computer Science & Engineering

⭐ Project Goal

The goal of this project is to demonstrate how Generative AI and workflow automation can be combined to automate technology research, information processing, analysis, and reporting.


### Your project is now nearly ready

Your folder should be:

```text
daily-ai-technology-intelligence-n8n/
│
├── README.md              ✅
├── workflow.json          ✅
├── sample-report.md       ⏳
│
├── screenshots/
│   ├── workflow-overview.png      ✅
│   ├── workflow-execution.png     ⏳
│   ├── ai-processing.png          ⏳
│   └── final-report.png           ⏳
│
└── demo/
    └── demo-video-link.txt        ⏳