# privacypolicycache
Privacy Policy Cache (Data Store)

  This repository holds the static JSON data for the Privacy Inspector extension.

  Why this exists
  Querying the LLM API every single time a user visits google.com or facebook.com is a
  waste of time and tokens. This repo acts as a public, read-only cache.

  How it works
   1. Read: The extension checks data/[domain].json before calling the AI.
   2. Write: If the file doesn't exist, the extension scans the page and uploads the
      result here automatically.

  Structure
  Files are stored by domain name in the /data folder.

   1 // Example: data/example.com.json
   2 {
   3   "url": "https://example.com/privacy",
   4   "scanned_at": "2026-02-06T15:00:00Z",
   5   "analysis": [ ... ]
   6 }

