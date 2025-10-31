# disaster-relief-assistant
AI-powered WhatsApp-based Disaster Relief Automation built with WorqHat No-Code Platform.

Problem Statement

During disasters such as floods, earthquakes, or landslides, communication channels often collapse.
Victims can send a WhatsApp message but struggle to reach rescue teams quickly.
Manual sorting and prioritization delay help, causing lives to be lost.

Goal

To build an automated WhatsApp-based disaster relief system that:

Interacts with users to collect name, location, and type of need.

Classifies the urgency level (High, Medium, Low).

Sends the request to the nearest NGO or rescue worker.

Escalates unresolved low-priority cases automatically after 24 hours.

Generates daily "Relief Distribution Reports."

Workflow Architecture
Trigger

WhatsApp Trigger – Activates when a user sends any message.

User Interaction

Bot asks for name, location, and type of help:

Medical Assistance → High Priority

Rescue → High Priority

Food/Water → Medium Priority

Shelter → Low Priority

AI Processing

Text Generation Node – Classifies request priority automatically.

Queue Storage

Database Node – Stores:
Name, Location, Need, Priority, Status, Timestamp

Escalation Logic

Time-Based Run – Every 24 hours:

Checks pending low-priority requests.

Upgrades them to high if unresolved.

Sends alerts to NGOs.

Notification

Send WhatsApp Node – Sends structured message to nearest NGO or rescue team.

Reporting

HTML to PDF + Send Mail Node – Generates and emails a "Relief Distribution Report" daily.

Example Workflow

A person sends "Help, flood in Chennai."

The bot replies asking for name, location, and type of need.

User replies with "Ravi, Chennai, Medical Assistance."

AI classifies as High priority.

Request is added to the database and forwarded to the nearest NGO.

If unresolved after 24 hours, it is reclassified as High and re-alerted.

A daily report of all requests is generated automatically.

Success Metrics

Average response time: under 5 minutes

AI accuracy for classification: over 90%

All requests tracked and escalated automatically

Tools and Technologies

WorqHat No-Code Platform

WhatsApp API

Google Maps API

Email and PDF Automation
import requests
url = 'https://api.worqhat.com/flows/trigger/a365632c-1849-4316-949e-cc66fec13c46'
api_key = 'wh_mhdbubft2wGEce9ofqfxb9obFkRUuiCpcV8sx62'
payload = {
    "messageId": "value1",
    "from": "value2",
    "to": "value3"
}
headers = {
    'Authorization': f'Bearer {api_key}',
    'Content-Type': 'application/json'
}
resp = requests.post(url, json=payload, headers=headers)
print(resp.status_code, resp.text)
