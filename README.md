# Telegram Media Downloader (Enhanced Fork)

Fork of [tangyoha/telegram_media_downloader](https://github.com/tangyoha/telegram_media_downloader).

## Enhancements

### 1. Media Group Sequential Numbering
When downloading media groups, files get sequential suffixes: caption_1.jpg, caption_2.jpg

**File:** module/app.py - get_caption_name()

### 2. file_unique_id Download Dedup
Skips duplicate downloads of forwarded content using Telegram's file_unique_id.
- Checks before download, records after success
- Persists downloaded IDs to data.yaml across restarts

**Files:** media_downloader.py, module/app.py

### 3. last_read_message_id Persistence
last_read_message_id now saves to data.yaml, surviving container restart.
Prevents re-scanning of historical messages.

**File:** module/app.py - update_config()

## Upstream
Original by [tangyoha](https://github.com/tangyoha). Licensed under MIT.
