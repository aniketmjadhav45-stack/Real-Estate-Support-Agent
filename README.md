# Real-Estate-Support-Agent
🚀 What This Workflow Does

This n8n automation works as an AI-powered real-estate assistant that responds to chat messages, schedules meetings, sends emails, checks availability, and logs everything into Airtable — all automatically.

It has two major branches based on the type of chat message:

Client wants to book a meeting → AI schedules the meeting, checks calendar, creates event, sends confirmation, and logs details.

General inquiries → AI replies with correct information and logs the interaction.

⚙️ Full Workflow Breakdown
1️⃣ Trigger: When chat message is received

The workflow starts whenever a user sends a WhatsApp/SMS/Chatbot message.

2️⃣ IF Condition – Message Type Identification

The message goes into an IF node that checks:

✔️ Does the message contain booking intent?

Examples:

“I want to book a site visit”

“Schedule a call”

“Can we meet tomorrow?”

If YES → Meeting Scheduling Flow
If NO → General Query Response Flow

🌿 BRANCH 1: Meeting Scheduling Flow (Upper Side)
3️⃣ AI Agent 1 – Understand request

AI analyzes the message:

Extracts date / time

Understands intent

Detects property interest

Retrieves user details (if stored in memory)

4️⃣ Google Gemini Chat Model

Supports the AI agent by interpreting natural language like:
🗓 “Next Tuesday evening”
🗓 “Tomorrow at 11 am”
🗓 “Can we meet this weekend?”

5️⃣ Simple Memory Node

Stores user history:

Previous conversations

Preferences

Property interests

Last meeting times

This makes the agent behave more human-like.

6️⃣ Google Calendar – Check Availability

The AI checks your Google Calendar to see if the requested time slot is free.

If slot is free → continue
If slot is not free → AI suggests next available time
7️⃣ Calculator Node

Used to format date/time for calendar and Airtable.

8️⃣ Gmail – Create Email Draft

An email is drafted to confirm the meeting:

Subject: Your Real Estate Meeting Is Confirmed
Body includes:

Time

Property details

Location

Support agent name

9️⃣ Airtable – Create Record

Meeting details are stored automatically:

Field	Info
Client Name	Auto extracted
Phone	Auto extracted
Requested Time	Extracted from message
Final Time	Confirmed slot
Email Sent	Yes
Property Type	Extracted

✔ Helps track all interactions in CRM style.

🌿 BRANCH 2: General Query Handling (Lower Side)
3️⃣ AI Agent – General Assistance

Handles questions like:

Property details

Price

Availability

Location

Policy

Documentation

Photos/amenities details

AI responds instantly with personalized answers.

4️⃣ Google Gemini Chat Model (General)

Understands and formats the best possible answer.

5️⃣ Simple Memory – Store conversation

The system remembers:

User’s preferred type of property

Budget range

Previously seen properties

Conversation tone

6️⃣ Airtable – Store Chat Record

Every conversation is logged for tracking.

7️⃣ Gmail – Send Email if Needed

If query requires follow-up, AI automatically sends an email reply with details.

🎯 WHY THIS WORKFLOW IS POWERFUL

✔ Fully automated client support
✔ Handles bookings + general queries
✔ AI extracts dates, times, preferences
✔ Auto emails + calendar integration
✔ Full CRM history in Airtable
✔ Works across WhatsApp, SMS, Websites

Perfect for real-estate agents, builders, property consultants, and sales teams.
