# Twilio MCP

An MCP server for Twilio communications. Send SMS, MMS, and WhatsApp messages. Make voice calls. Manage phone numbers.

## What it does

Connect your Twilio account to any MCP client. Send text messages, share images, make phone calls, and manage your phone numbers through natural language.

## Tools

- send_sms. Send an SMS text message.
- send_mms. Send an MMS message with an image or media file.
- send_whatsapp. Send a WhatsApp message.
- get_message_status. Check delivery status of a sent message.
- list_messages. View recent message history with filters.
- make_call. Initiate a voice call with TwiML control.
- list_calls. View recent call history.
- list_numbers. List your Twilio phone numbers.
- search_numbers. Search available phone numbers by area code.

## Authentication

Set these environment variables:

```bash
export TWILIO_ACCOUNT_SID="ACxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
export TWILIO_AUTH_TOKEN="your-auth-token"
```

Find these in your Twilio Console dashboard.

## Install

```bash
npx twilio-mcp
```

## Claude Desktop setup

```json
{
  "mcpServers": {
    "twilio": {
      "command": "npx",
      "args": ["-y", "twilio-mcp"],
      "env": {
        "TWILIO_ACCOUNT_SID": "ACxxxxxxxx",
        "TWILIO_AUTH_TOKEN": "your-token"
      }
    }
  }
}
```

## Example usage

Ask Claude:

"Send an SMS to +14155551234 saying 'Hello from Claude' from my Twilio number"

"Send a WhatsApp message to +14155551234 with this image attached"

"What is the delivery status of message SM1234567890?"

"List my recent messages from the last day"

"Call +14155551234 and play a message using this TwiML URL"

"List my Twilio phone numbers"

"Search for available phone numbers in area code 415"

## Voice calls

To make calls, you need a TwiML URL that controls the call flow. You can use TwiML Bin in the Twilio Console or host your own TwiML. Example TwiML:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<Response>
  <Say voice="alice">Hello, this is a call from your AI assistant.</Say>
</Response>
```

## License

MIT
