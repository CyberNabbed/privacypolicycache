# Privacy Policy Cache (Data Store)

This repository holds the static JSON data for the **Privacy Inspector** extension.

## Why this exists

Querying the LLM API every single time a user visits high-traffic sites (e.g., `google.com` or `facebook.com`) is a waste of time and tokens.

This repo acts as a **public, read-only cache** to optimize performance and reduce costs.

## How it works

* ** Read:** The extension checks `data/[domain].json` before calling the AI.
* ** Write:** If the file doesn't exist, the extension scans the page and uploads the result here automatically.

## Structure

Files are stored by domain name in the `/data` directory.

```json
// Example: data/example.com.json
{
  "url": "[https://example.com/privacy](https://example.com/privacy)",
  "scanned_at": "2026-02-06T15:00:00Z",
  "analysis": [ ... ]
}
