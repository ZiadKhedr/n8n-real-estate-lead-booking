# Real Estate Lead Qualification and Booking

[Watch the demo on YouTube](https://youtu.be/LAyx-xgaRps) · [Download the n8n workflow](bigin.json)

A Telegram assistant that gathers property requirements, books consultations, and records them in Zoho Bigin. The demo follows a sample Dubai property inquiry through the Telegram confirmation, Google Calendar invite, and Bigin contact and appointment.

## What I built

- A multi-turn n8n AI agent using Meta Muse Spark to collect buyer requirements and confirm a preferred consultation time.
- A Google Calendar availability check and booking flow that creates a Google Meet link and sends a calendar invitation.
- Bigin API calls that upsert the buyer as a contact and create a linked appointment. The bot replies in Telegram with the meeting details.

## Run it in n8n

1. Import [`bigin.json`](bigin.json) into n8n.
2. Set the same Telegram bot credential on **Telegram Trigger** and **Telegram Reply**.
3. Connect **Meta Muse Spark** to your Meta Model API credential with base URL `https://api.meta.ai/v1` and model `muse-spark-1.3`.
4. Connect both Google Calendar tools to your Google account and select the same calendar on both nodes. The account needs permission to book events and add Google Meet conferencing.
5. Connect both Bigin tools to an n8n Header Auth credential. Use `Authorization` as the header name and `Zoho-oauthtoken <access_token>` as its value. Use your Zoho data center's API domain and grant Contacts write and Events create scopes. The demo uses a short-lived access token.
6. Test with a sample inquiry and an email address you control. Confirm the Telegram reply, calendar event and invitation, and the linked contact and appointment in Bigin.
