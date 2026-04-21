# Component: API Scheduler

## Purpose

Upload and schedule months of Google Business Profile posts in a single operation using a third-party posting platform's API.

---

## How It Works

After the language database generated post drafts and the quality review was complete, the posts needed to be scheduled for publication. Publishing manually, even with a scheduling tool, would have required uploading each post individually, which still required significant labor at scale.

A third-party posting platform offered API access for bulk scheduling. A custom integration built in JavaScript and Google Sheets connected the finalized post drafts to the API. The integration formatted each post as a payload with the post text, paired image, target Google Business Profile, and scheduled publication date and time, then uploaded the entire batch in one operation.

Once uploaded, posts published automatically on their scheduled dates without any further action required.

---

## Design Notes

The posting platform API was the critical dependency. Finding a platform that both offered API access for bulk scheduling and worked reliably with Google Business Profiles was a meaningful part of the research for this project. Once identified, the integration itself was relatively straightforward.

The scheduling logic spread posts across the coming months with variation in publication times to avoid a pattern that might look automated to Google's algorithms.

---

[Back to GBP Automation](../../README.md)
