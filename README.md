# 🔭 Astrophysics Daily News Report

Automated daily astrophysics news scraper that searches for the latest astrophysics news and sends an email report.

## Features

- ✅ **Daily Automation** - Runs automatically every day at 9:00 AM UTC
- ✅ **Facebook & Public Sources** - Searches Facebook public posts and astronomy news sites
- ✅ **Email Reports** - Sends formatted HTML email with max 10 news items
- ✅ **No Manual Setup** - Fully automated via GitHub Actions
- ✅ **Secure Credentials** - Uses GitHub Secrets for sensitive data

## Setup Instructions

### 1. GitHub Secrets Configuration

Add the following secrets to your GitHub repository:

1. Go to: **Settings** → **Secrets and variables** → **Actions** → **New repository secret**

2. Add these three secrets:

| Secret Name | Value | Example |
|-------------|-------|---------|
| `GMAIL_USER` | Your Gmail address | `your-email@gmail.com` |
| `GMAIL_PASSWORD` | Gmail app-specific password* | `xxxx xxxx xxxx xxxx` |
| `RECIPIENT_EMAIL` | Email to receive reports | `your-email@gmail.com` |

*[How to generate Gmail app password](https://support.google.com/accounts/answer/185833)

### 2. Schedule Configuration

The workflow runs daily at **9:00 AM UTC**. To change the time:

1. Edit `.github/workflows/daily_astro_news.yml`
2. Modify the `cron` schedule line:
   ```yaml
   - cron: '0 9 * * *'  # Change '9' to your desired hour (0-23)
   ```

### 3. Manual Testing

To test the workflow manually:

1. Go to **Actions** tab in your repository
2. Select **Daily Astrophysics News Report**
3. Click **Run workflow**
4. Check email inbox within a few minutes

## How It Works

1. **Scheduled Trigger** - Runs automatically via GitHub Actions cron schedule
2. **News Scraping** - Searches Facebook public posts and astronomy news sites
3. **Report Generation** - Creates formatted HTML email with max 10 news items
4. **Email Delivery** - Sends report to your email address via Gmail
5. **Logging** - Records execution details in artifacts

## Email Report Format

Each report includes:
- 📅 **Date and Time**
- 📝 **News Title** - Main headline
- 📄 **Summary** - Brief description
- 🔗 **Link** - Direct link to full story
- 📍 **Source** - Where the news came from

## Limitations

- Maximum 10 news items per report (configurable in script)
- Requires valid Gmail credentials with app-specific password
- Facebook direct scraping is limited; also pulls from public astronomy sources

## Troubleshooting

### No email received?
- Check GitHub Actions logs: **Actions** tab → workflow run
- Verify Gmail secrets are correctly set
- Check spam/trash folder

### Workflow not running?
- Go to **Actions** → **Daily Astrophysics News Report**
- Check if workflow is enabled (toggle on the right)
- Verify cron schedule in `.github/workflows/daily_astro_news.yml`

### Modified Code?
- Simply push changes to the repository
- No manual restart needed - changes apply automatically

## Files

- `astro_news_scraper.py` - Main scraping and email logic
- `requirements.txt` - Python dependencies
- `.github/workflows/daily_astro_news.yml` - Automation workflow

## Support

For issues or questions:
1. Check GitHub Actions logs
2. Review error messages in workflow runs
3. Verify all secrets are correctly configured

---

**Fully Automated** - No manual intervention required! ✨
