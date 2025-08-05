# AI Instagram Trend Generator

This n8n workflow automates the creation and posting of Instagram content based on current trends. It scrapes popular images from specified hashtags, uses AI to generate new captions and images, and posts them to your Instagram account.

## Features

- **Trend Scraping**: Fetches top-performing image posts from Instagram hashtags using the Instagram Scraper API on RapidAPI.
- **Duplicate Prevention**: Checks a PostgreSQL database to ensure content is not reposted.
- **AI Content Creation**:
  - Uses OpenAI's GPT-4 Vision to analyze the trend image.
  - Generates a new, relevant caption for the post.
  - Uses Replicate (Flux AI) to generate a new, unique image inspired by the trend.
- **Automated Posting**: Publishes the generated image and caption to an Instagram Business account.
- **Scheduled Execution**: Runs on a schedule to consistently post new content.
- **Notifications**: Sends status updates and error alerts to a Telegram chat.

## Prerequisites

- An n8n instance.
- An Instagram Business Account ID.
- A Telegram Bot and Chat ID.
- A RapidAPI key with a subscription to the [Instagram Scraper API](https://rapidapi.com/social-api1-instagram/api/instagram-scraper-api2).
- A Replicate API Token.
- An OpenAI API Key.
- A PostgreSQL database with the `top_trends` table created (see schema in the workflow's sticky notes).

## Setup

1.  **Import `ai_instagram_trend_generator.json` into n8n.**
2.  **Set up your database**: Create the `top_trends` table in your PostgreSQL database using the schema provided in the workflow.
3.  **Add your credentials/parameters** in the designated "Set" nodes:
    - **Replicate params**: Your Replicate API token.
    - **Instagram params**: Your Instagram Business Account ID.
    - **Telegram Params**: Your Telegram Chat ID.
    - **Rapid Api params**: Your RapidAPI key.
    - **OpenAI**: Add your credentials to the "Analyze Image..." and "Analyze Content..." nodes.
    - **PostgreSQL**: Configure the "Check Data on Database Is Exist" and "insert data on db" nodes with your database credentials.
4.  **Customize Hashtags**: In the "get top trends..." HTTP Request nodes, change the hashtags (`blender3d`, `isometric`) to topics relevant to your account.
5.  **Activate the workflow.**
