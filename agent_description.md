# Trading News Agent

A financial market intelligence agent that tracks companies in specific sectors or themes, analyzes news sentiment, and generates investment recommendations using Google's Gemini AI.

## Overview

This agent continuously monitors news and market information for companies within a user-specified market sector or theme (e.g., "US Semiconductor Market", "AI Chip Manufacturers"). It performs sentiment analysis on recent news and provides actionable investment recommendations with justifications.

## Main Functions

- **Company Identification**: Automatically identifies relevant publicly traded companies, currencies, cryptocurrencies, or bonds based on the specified market theme
- **News Monitoring**: Fetches and aggregates recent news articles for each tracked company using Google Search grounding
- **Sentiment Analysis**: Analyzes news sentiment and relevance scores for market intelligence
- **Investment Recommendations**: Generates clear, actionable investment recommendations (Long/Short/Neutral) with justifications and hypothetical scenarios
- **Continuous Monitoring**: Runs hourly cycles to keep information and recommendations up-to-date

## Key Features

- Interactive setup allowing users to specify their market of interest
- Maintains a curated list of facts for each company (up to 30 most relevant facts)
- Provides recommendations in format: "TICKER (Sentiment: Long/Short/Neutral): Justification"
- Includes hypothetical scenario analysis for each recommendation
- Automatic deduplication of news facts to avoid redundancy

## Inputs

- **User Input** (via stdin): Market sector or theme to track (e.g., "US Semiconductor Market")
- **Environment Variable**: `GEMINI_API_KEY` - Required for Google Gemini AI authentication

## Outputs

- **Console Output** (stdout):
  - List of identified companies with tickers
  - News summaries with relevance and sentiment scores
  - Investment recommendations with justifications
  - Hourly cycle summaries
  - Status updates and progress indicators

## Operation

The agent runs continuously once started, performing hourly analysis cycles. Each cycle:
1. Fetches latest news for all tracked companies
2. Updates and prunes the fact database
3. Generates fresh investment recommendations
4. Displays a comprehensive summary

The agent can be stopped at any time using keyboard interrupt (Ctrl+C).