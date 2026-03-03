---
name: email-outreach
description: Generate and send personalized cold outreach emails.

input_schema:
  type: object
  properties:
    lead:
      type: object
    offer_details:
      type: string

output_schema:
  type: object
  properties:
    email_subject:
      type: string
    email_body:
      type: string
    send_status:
      type: string
---
instructions: |
  Generate personalized email including:
  - First name
  - Company name
  - Website insights
  - Pain point
  - Value proposition
  - Clear CTA

  Use professional tone.
  Keep under 150 words.

  Mark send_status as:
  - ready_to_send
  - sent
  - failed
