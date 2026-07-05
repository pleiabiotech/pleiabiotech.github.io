# PLEIA site

Static site with Telegram booking links.

## Booking bot

Primary CTAs open the PLEIA Telegram bot:

- Event booking: `https://t.me/pleia_applications_bot?start=july9`
- Private request: `https://t.me/pleia_applications_bot?start=private`
- Corporate request: `https://t.me/pleia_applications_bot?start=corporate`

The bot source lives in `../bot`. It asks guests to choose an experience, enter their name, pay to Revolut `@Rodionovakate` or full bank transfer details, send a screenshot, and waits for support confirmation.

## Telegram applications

There is no browser application form anymore. Website buttons send guests directly to `@pleia_applications_bot`, where the full booking journey happens.

Set these environment variables in the deploy provider:

```bash
TELEGRAM_BOT_TOKEN=your_bot_token
TELEGRAM_CHAT_IDS=123456789
```

For multiple recipients, use comma-separated chat IDs:

```bash
TELEGRAM_CHAT_IDS=123456789,987654321
```

Katya needs to open `@pleia_applications_bot` and press `/start` before the bot can message her. After that, her numeric `chat_id` can be used as the bot `SUPPORT_CHAT_ID`.
