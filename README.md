# disaster-relief-assistant
AI-powered WhatsApp-based Disaster Relief Automation built with WorqHat No-Code Platform.
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
