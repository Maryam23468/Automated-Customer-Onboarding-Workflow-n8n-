# Automated-Customer-Onboarding-Workflow-n8n-

## Overview
This project implements an automated customer onboarding workflow using n8n. The workflow collects new customer data from forms or a CRM, triggers multi-step onboarding tasks, and integrates with various platforms to ensure a smooth onboarding experience.

## Demo Video
-**https://www.loom.com/share/2a203ba1b03944e39228f7f269aef509?sid=46881c5f-7be6-43b0-b645-18cae34e16e7**

## Features
- **Automated Data Collection:** Collect new customer data automatically from forms or CRM systems.
- **Multi-Step Onboarding:** Trigger tasks such as sending welcome emails, creating accounts, and notifying the support team via Slack or email.
- **API Integrations:** Seamless integration with tools like Gmail, Slack, and various CRM systems for real-time updates and data flow.

## Workflow Structure
The workflow consists of the following main components:

1. **Schedule Trigger:** Initiates the workflow at specified intervals.
2. **Search Records:** Queries the Airtable database for customers who have not yet been onboarded.
3. **Send Welcome Email:** Sends a personalized welcome email to the new customer using Gmail.
4. **Update Record:** Updates the Airtable record to mark the customer as onboarded.
5. **HTTP Request:** Sends customer information to an external endpoint for further processing (e.g., webhook).
6. **Notify Support Team:** Sends a notification email to the support team with the new customer's details.

## Installation

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/yourusername/automated-customer-onboarding-workflow.git
   cd automated-customer-onboarding-workflow
   ```

2. **Set Up n8n:**
   - Ensure you have n8n installed. You can follow the [n8n installation guide](https://docs.n8n.io/getting-started/installation/).

3. **Configure API Credentials:**
   - Set up your Airtable and Gmail API credentials in n8n to enable the workflow to access these services.

4. **Import the Workflow:**
   - Open n8n and import the workflow JSON file provided in this repository.

## Usage
- **Triggering the Workflow:**
  - The workflow will automatically run based on the configured schedule. You can also manually trigger it from the n8n dashboard.

- **Monitoring:**
  - Monitor the workflow execution and logs through the n8n interface to ensure everything is functioning correctly.

## Workflow JSON
The workflow is defined in JSON format. Below is the structure of the workflow:

```json
{
  "name": "My workflow",
  "nodes": [
    {
      "parameters": {
        "rule": {
          "interval": [
            {
              "field": "minutes"
            }
          ]
        }
      },
      "type": "n8n-nodes-base.scheduleTrigger",
      "typeVersion": 1.2,
      "position": [0, 0],
      "id": "836db8d6-a74d-4b78-8cd6-b082fec5c140",
      "name": "Schedule Trigger"
    },
    ...
  ],
  "connections": {
    ...
  },
  "active": false,
  "settings": {
    "executionOrder": "v1"
  },
  "versionId": "de516d2f-b956-46c9-9474-46356cc9ba87",
  "meta": {
    "templateCredsSetupCompleted": true,
    "instanceId": "17def896bb5cda64f462f6a10d9e0c1abe06e5ba21af0af4d2ce3a218029932e"
  },
  "id": "RIaFMH609lXGcsIb",
  "tags": []
}
```

## Contributing
If you would like to contribute to this project, feel free to submit a pull request or open an issue for any enhancements or bugs.


## Acknowledgments
- [n8n](https://n8n.io/) for providing an excellent workflow automation tool.
- [Airtable](https://airtable.com/) for easy database management.
- [Gmail API](https://developers.google.com/gmail/api) for sending emails.

