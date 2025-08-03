# Drive Mate
# 📦 n8n Workflow + Twilio Sandbox + Google Drive

<img width="1408" height="549" alt="image" src="https://github.com/user-attachments/assets/b0539ff7-c526-4035-aeea-294c4aa5b740" />


This project includes an `n8n` workflow that enables interaction with users via Twilio Sandbox WhatsApp messaging and manages files on Google Drive. It performs operations like LIST, DELETE, MOVE, or SUMMARIZE a file/folder in the user's Google Drive using OAuth

## 🚀 Features

- List files from the user's Google Drive
- Reply via WhatsApp using Twilio Sandbox
- Delete/move files based on commands

## 📁 Contents

- `workflows/`: Contains the exported n8n workflow.
- `helpers/`: Helper scripts used in custom code nodes.
- `.env.sample`: Template for environment variables.

## 🧪 WhatsApp Twilio Sandbox Setup

1. Go to [Twilio Console – Messaging](https://console.twilio.com/)
2. Activate **Sandbox for WhatsApp**
3. Follow the prompt to send a join code to the number shown
4. Use the sandbox number in your `.env` like this:


## 🔐 Google Drive API Setup

1. Go to Google Cloud Console
2. Create a new project or use an existing one
3. Enable Google Drive API
4. Create OAuth 2.0 Client ID credentials
5. Download the JSON file and configure it inside the n8n credentials, like the Client ID and Client Secrets
6. Use Search, List, Delete, or Move operations via the Drive node.

# 💬 WhatsApp Command Syntax

## Users send one of the following commands to the Twilio WhatsApp number:

list
### → Lists all files in the Google Drive root folder

delete <filename>
### → Deletes the specified file from Drive
### Example:
delete image.png

move <filename>
### → Moves the specified file to a different folder
### Example:
move report.pdf

# 📍 Notes: SUMMARIZE and MOVE commands are not working yet
# - Command parsing is handled in the `Get Data` and `Switch` modules.
# - The flow routes the command to the appropriate Google Drive operation (list, delete, move) and replies to the user accordingly.
