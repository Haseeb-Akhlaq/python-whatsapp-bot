# AI Slackbot HR Assistant with OpenAI Assistant API

Build an interactive Slackbot HR Assistant using the OpenAI Assistant API, Python, and Flask. This guide will show you how to create a Slackbot that leverages OpenAI's powerful AI capabilities for generating responses and Airtable for data storage.

## Prerequisites

- **OpenAI Account**: Sign up for an account at [OpenAI](https://platform.openai.com/) if you don't have one.
- **Slack App**: Create a Slack app at [Slack API](https://api.slack.com/).
- **Digital Ocean**: We'll use Digital Ocean for deployment.
- **Python Knowledge**: Basic understanding of Python programming.

## Getting Started

### Step 1: Create a Slack App

1. Visit [Slack API](https://api.slack.com/).
2. Create a new App with an App Manifest.
3. Configure your App Manifest as shown below:

    ```json
    {
        "display_information": {
            "name": "HY"
        },
        "features": {
            "bot_user": {
                "display_name": "HY",
                "always_online": true
            }
        },
        "oauth_config": {
            "scopes": {
                "bot": [
                    "app_mentions:read",
                    "chat:write",
                    "im:history",
                    "users:read"
                ]
            }
        },
        "settings": {
            "event_subscriptions": {
                "request_url": "https://f526-148-252-141-35.ngrok-free.app/slack/events",
                "bot_events": [
                    "app_mention",
                    "message.im"
                ]
            },
            "org_deploy_enabled": false,
            "socket_mode_enabled": false,
            "token_rotation_enabled": false
        }
    }
    ```

### Step 2: Set Up the Project

1. Obtain your OpenAI API key.
2. Insert the **SLACK_BOT_TOKEN** and **SLACK_SIGNING_SECRET** into your project.
3. Create a new table in Airtable and generate an API token for it.
4. Update your project with the Airtable URL.

### Step 3: Deployment

Deploy the application to the Digital Ocean App

### Step 3: Integrate with Slack
1. In your Slack App's settings, go to 'Event Subscriptions'.
2. Enter the URL of your deployed application to integrate it with Slack.
