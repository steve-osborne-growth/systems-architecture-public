# License Assignment Validation Tool

A self-serve tool that lets sellers instantly see which customer users count toward billing and which are filtered out, replacing a daily manual PDF review process.

*This tool has been retired. The functionality is now built into the main dashboard.*

---

## The Problem

For several years, there was no way for anyone to see at the individual user level who was being counted toward a customer's license billing and who was being filtered out. The only path was for a customer to export a list of their assigned users, send the PDF to a seller, and then the seller would forward it to me for a manual line-by-line review.

This happened almost daily, sometimes multiple times a day. The work was entirely manual, completely mindless, and a poor use of time for everyone involved.

---

## How It Works

1. A customer sends a PDF of their assigned users to a seller
2. The seller uses Trimble Assistant to extract the user list into plain text
3. The seller pastes the extracted users into the License Assignment Validation Google Sheet
4. The sheet automatically highlights each user in green or red based on whether they count toward billing

Behind the scenes, the tool replicates the SQL filtering logic used in the billing pipeline, converted into a regex formula running via Google Apps Script. The filtering criteria are hidden from the seller. They see only the result: counted or not counted.

---

## Tech Used

- Google Sheets (interface)
- Google Apps Script (JavaScript)
- Trimble Assistant (PDF text extraction)
- SQL to regex conversion for the filtering logic

---

## Time to Build

Approximately two to three hours including testing and adjustments for distribution.

---

## Impact

No direct monetary impact. The tool eliminated a daily source of friction between sellers and the program operator for 18 months until the functionality was permanently built into the main dashboard. It solved a problem that multiple sellers experienced daily and removed a repetitive manual task that had no business being done by a human.

---

## AI Angle

AI was used to help convert the original SQL filtering query into a regex formula. The actual user validation does not use AI because accuracy is critical and a deterministic data match is more reliable than a model prediction for this use case.

---

## Links

- [License Assignment Validation Tool (Retired)](#)

---

[Back to micro systems](../README.md)
