---
name: crm-integration
description: Sync qualified leads to CRM platforms like HubSpot or Zoho.

input_schema:
  type: object
  properties:
    leads:
      type: array
    crm_platform:
      type: string
    api_key:
      type: string

output_schema:
  type: object
  properties:
    sync_status:
      type: string
    records_created:
      type: number
    records_updated:
      type: number
---

instructions: |
  Connect securely to selected CRM platform.
  If crm_platform = "hubspot":
    - Create or update Contact
    - Map fields: name, email, company, lead_score, qualification_status
  If crm_platform = "zoho":
    - Create or update Lead module entry
  Prevent duplicate creation by checking email.
  Return summary of records created and updated.
  Never expose API keys in output.
