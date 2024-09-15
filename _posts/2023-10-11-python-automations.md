---
layout: post
title: "How I Built My Automations in Python"
---
Automation has been a game-changer for my productivity and day-to-day workflow. Whether it's managing emails, updating spreadsheets, or sending reminders, I've found Python to be the perfect tool to take these repetitive tasks off my plate and let me focus on the more important stuff.

So, in this post, I’ll take you through how I built some of my favourite automations in Python. Don’t worry, I’ll keep things simple—no unnecessary technical jargon. Let’s dive in!

---

### Why Python for Automation?

There are plenty of automation tools and languages out there, so why Python? For me, it boils down to three things:

1. **Simplicity** – Python is easy to learn, read, and write. Its syntax is clean and intuitive.
2. **Libraries** – There are libraries for almost anything you want to automate. Need to send an email? There’s `smtplib` for that. Want to manipulate an Excel spreadsheet? Use `openpyxl`. Need web scraping? `BeautifulSoup` has your back.
3. **Community** – Python has a massive, active community. This means if you ever get stuck, there are heaps of tutorials and Stack Overflow threads to help you.

### Step 1: Defining the Tasks

Before I dove head-first into coding, I needed to identify **what** I wanted to automate. Here are a few of the tasks that stood out to me:

- **Daily Email Digest**: Each morning, I get bombarded with emails from various newsletters, services, and updates. I wanted a daily summary of important emails.
  
- **File Organisation**: My Downloads folder was a warzone. Automating the sorting of files into specific folders seemed like a natural first step.
  
- **Web Scraping for Reports**: I wanted to scrape websites and collect data to generate weekly reports—saves me hours of manual data entry.

- **Automated Data Backups**: I wanted a script to back up specific directories to a cloud service once a week, so I never worry about losing important files.

---

### Step 2: Setting Up the Environment

To get started, I needed to set up my Python environment. For that, I followed these simple steps:

1. **Install Python** – Python can be downloaded from the official [Python website](https://www.python.org/). I made sure to grab the latest version (at the time, Python 3.11).
   
2. **Install a Code Editor** – I use Visual Studio Code (VSCode), which is lightweight and comes with great extensions for Python.

3. **Create Virtual Environments** – One of the first lessons I learned was to keep each project isolated in its own virtual environment. This way, I could install the necessary packages without them clashing with other projects. I used Python’s built-in `venv` module:

   ```bash
   python3 -m venv myprojectenv
   source myprojectenv/bin/activate  # For MacOS/Linux
   ```

4. **Install Libraries** – With the environment set up, I installed the necessary libraries for my projects using `pip`:

   ```bash
   pip install openpyxl smtplib beautifulsoup4
   ```

---

### Step 3: Automating Email Summaries

For my **Daily Email Digest**, I used Python’s `smtplib` to send emails and `imaplib` to fetch messages from Gmail. Here’s how I set it up:

1. **Access Gmail via IMAP**: I used `imaplib` to connect to my Gmail inbox and grab unread messages:

   ```python
   import imaplib
   import email

   mail = imaplib.IMAP4_SSL('imap.gmail.com')
   mail.login('your-email@gmail.com', 'your-app-password')
   mail.select('inbox')

   # Search for all unread emails
   status, messages = mail.search(None, 'UNSEEN')
   ```

2. **Extracting Relevant Info**: I parsed the fetched emails using the `email` library to get the subject lines and sender addresses.

3. **Sending the Digest**: Once I had the email data, I used `smtplib` to send a nicely formatted email to myself with a summary of new messages:

   ```python
   import smtplib
   from email.mime.text import MIMEText

   msg_content = "Here are your unread emails:\n"
   msg = MIMEText(msg_content)

   msg['From'] = 'your-email@gmail.com'
   msg['To'] = 'your-email@gmail.com'
   msg['Subject'] = 'Daily Email Summary'

   with smtplib.SMTP_SSL('smtp.gmail.com', 465) as server:
       server.login('your-email@gmail.com', 'your-app-password')
       server.sendmail('your-email@gmail.com', 'your-email@gmail.com', msg.as_string())
   ```

### Step 4: Automating File Organisation

Next on the list was my messy Downloads folder. I created a script that automatically sorted files based on their extension. Here’s how it went down:

1. **Walk the Downloads Folder**: I used Python’s `os` module to scan through all files:

   ```python
   import os
   import shutil

   folder = '/Users/matt/Downloads'

   for filename in os.listdir(folder):
       if filename.endswith('.pdf'):
           shutil.move(os.path.join(folder, filename), '/Users/matt/Documents/PDFs')
       elif filename.endswith('.jpg') or filename.endswith('.png'):
           shutil.move(os.path.join(folder, filename), '/Users/matt/Pictures')
   ```

2. **Automation with Task Scheduler**: I didn’t want to run this script manually every day, so I set it up to run daily via macOS’s **Launchd** or Windows **Task Scheduler**. A simple cron job does the trick on Linux too.

---

### Step 5: Web Scraping for Reports

To automate the gathering of data for my weekly reports, I turned to **web scraping**. I used `BeautifulSoup` and `requests` to scrape the relevant sites:

1. **Fetch the Web Page**: First, I grabbed the page content with the `requests` library:

   ```python
   import requests
   from bs4 import BeautifulSoup

   page = requests.get("https://example.com/data")
   soup = BeautifulSoup(page.content, 'html.parser')
   ```

2. **Parse the Data**: Using BeautifulSoup’s intuitive syntax, I extracted the data I needed:

   ```python
   data = soup.find_all('div', class_='data-class')
   for item in data:
       print(item.text)
   ```

3. **Generate a Report**: Once I had the data, I used `openpyxl` to write it into an Excel file that I could then email to myself:

   ```python
   from openpyxl import Workbook

   wb = Workbook()
   ws = wb.active

   ws.append(["Header 1", "Header 2", "Header 3"])
   ws.append([data1, data2, data3])

   wb.save('weekly_report.xlsx')
   ```

---

### Step 6: Automating Backups

Finally, I set up an automated backup system using `shutil` to zip files and upload them to a cloud service (like Google Drive) via API:

1. **Zipping the Folder**: I used the `shutil` module to create a compressed backup of the folder:

   ```python
   shutil.make_archive('backup', 'zip', '/path/to/your/folder')
   ```

2. **Upload to Google Drive**: I integrated the Google Drive API to upload the zipped file. Google provides a handy Python client library, which I found in their official documentation.

---

### Wrapping It Up

Building these Python automations wasn’t as hard as I expected. Sure, it took some tinkering, but the payoff has been massive. I now have my emails summarised daily, my files organised, and my reports generated without lifting a finger.

If you're looking to automate some of your workflows, I’d recommend giving Python a go. It’s flexible, powerful, and the community is fantastic. Plus, once you get the hang of it, you’ll be automating things you never thought possible.

And remember, with every line of code, you're not just saving time—you’re giving your future self a gift of less hassle. Keep automating, folks! 

---

**Tools I Used:**
- **VSCode**: For writing and running Python scripts.
- **smtplib** and **imaplib**: For handling emails.
- **BeautifulSoup** and **requests**: For web scraping.
- **openpyxl**: For working with Excel files.
- **shutil**: For managing files and directories.

That’s it for now! If you have any questions or want to share your own automations, feel free to drop a comment.