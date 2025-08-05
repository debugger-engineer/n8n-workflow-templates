# Social Media Uploader Workflow

This n8n workflow automates the process of posting videos to social media. It watches a Google Drive folder for new videos, generates a caption using AI, and then uploads the video and caption to TikTok and Instagram.

## Features

- **Google Drive Integration**: Triggers when a new video is added to a specified folder.
- **AI-Powered Content Generation**: Uses OpenAI to transcribe the video's audio and generate a compelling caption.
- **Multi-Platform Upload**: Posts the video to both TikTok and Instagram via the `upload-post.com` API.
- **Error Notifications**: Sends a message to a Telegram chat if an error occurs.

## Prerequisites

- An n8n instance.
- A Google Drive account.
- An OpenAI API key.
- A Telegram bot token and chat ID for notifications.
- An account and API token from `upload-post.com`.

## Setup

1.  **Import `social_media_uploader.json` into n8n.**
2.  **Configure the "Google Drive Trigger"** node to watch your desired folder.
3.  **Add your credentials**:
    - **OpenAI**: In the "Get Audio from Video" and "Generate Description..." nodes.
    - **Telegram**: In the "Telegram" node, set your `chatId`.
    - **upload-post.com**: In the "Upload Video..." nodes, add your API key to the headers (`Authorization: Apikey YOUR_TOKEN_HERE`).
4.  **Customize the prompt** in the "Generate Description..." node to match your brand's voice.
5.  **Activate the workflow.**
