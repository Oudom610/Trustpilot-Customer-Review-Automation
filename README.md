# Trustpilot-Customer-Review-Automation - n8n Workflow

Automated Trustpilot review analysis system that scrapes recent reviews, extracts insights using AI, and saves results to Google Sheets.

## What It Does

1. **Scrapes Trustpilot reviews** from the last 30 days for any company
2. **Extracts review data** (author, rating, date, title, text, country) using AI
3. **Analyzes sentiment and topics** with comprehensive business insights
4. **Saves results** to Google Sheets in two formats:
   - Raw review data
   - AI-generated analysis report

## Features

- **Smart pagination**: Automatically stops when reaching reviews older than 30 days
- **Batch processing**: Handles large volumes efficiently with configurable batch sizes
- **Rate limiting**: Built-in delays to respect Trustpilot's servers
- **AI-powered analysis**: Uses Gemini 2.0 Flash for sentiment analysis and business recommendations
- **Dual output**: Both raw data and executive summary saved to Google Sheets

## Configuration

Edit the "Set Configuration" node to customize:

```javascript
company_domain: "mexipass.com"    // Target company domain
days_back: 30                    // How many days back to analyze
batch_size: 10                   // Reviews per batch
```

## Required Credentials

1. **OpenRouter API** - For AI analysis (Gemini 2.0 Flash model)
2. **Google Sheets OAuth2** - For saving results

## Output Structure

### Analysis Report Includes:
- **Sentiment Analysis**: Overall sentiment and review volume
- **Topic Extraction**: Most mentioned customer topics
- **Operational Insights**: Top 3 problems to fix
- **Competitive Intelligence**: Competitor mentions and switching patterns
- **Recommended Actions**: Priority business improvements

### Raw Data Includes:
- Author name
- Star rating (1-5)
- Review date
- Review title
- Full review text
- Reviewer country

## How to Use

1. Import the workflow JSON file
2. Set up required credentials (OpenRouter + Google Sheets)
3. Configure your target company domain
4. Click "Test workflow" to run
5. Check your Google Sheets for results

## Technical Notes

- Uses AI information extraction for consistent data parsing
- Implements workflow static data for accumulating results across batches
- Creates dated sheets for raw data organization
- Includes retry logic and error handling for web requests

## License

Open source - modify as needed for your use case.
