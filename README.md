# Tele - AI Meeting & Welcome Bot

This is a powerful Telegram bot that manages meetings, welcomes new members, and provides AI-driven scheduling.

## Features

*   **AI Meeting Manager**:
    *   Parses natural language meeting requests (via ChatGPT-4o).
    *   Supports Zoom copy-paste formats perfectly.
    *   Sends reminders (1h, 15m, starting now).
    *   Restricted to "Zoom Alerts" chat only.
*   **Sales Team Welcome**:
    *   Automatically welcomes new members in "Inception Sales Team".
    *   Includes a training video link.
    *   Manual trigger via `/announce`.
*   **Website Integration**:
    *   Accepts Webhook POST requests to schedule meetings instantly.
    *   Chat ID lookup command: `/id`.

## Installation

1.  Clone the repository:
    ```bash
    git clone https://github.com/rotmgamali/tele.git
    cd tele
    ```

2.  Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```

3.  Configure Environment:
    Create a `.env` file with your keys:
    ```bash
    TELEGRAM_BOT_TOKEN="7224632370:..."
    OPENAI_API_KEY="sk-..."
    ```
    *(Note: Keys are currently hardcoded in main.py for ease of use, but .env is recommended)*

4.  Run:
    ```bash
    python main.py
    ```

## Commands

*   `/start` - Wake up the bot.
*   `/meetings` - List upcoming scheduled meetings.
*   `/id` - Get the current Chat ID (for API integration).
*   `/announce [Name]` - Manually trigger the Welcome Message.

## API Usage (Webhook)

Send a POST request to:
`https://api.telegram.org/bot<TOKEN>/sendMessage`

JSON Body:
```json
{
  "chat_id": "-5102728176",
  "text": "New Website Booking! \nTopic: Consultation\nTime: 2026-03-01 15:00\nLink: https://zoom.us/..."
}
```
