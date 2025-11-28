# Setup Guide - Consulting Services Chatbot

## Prerequisites
- Zoho account (free developer tier)
- Google Cloud Console account
- Twilio account (free trial)
- Stripe account (optional, for payment)

## Step 1: Create Zoho SalesIQ Bot

1. Sign in to https://www.zoho.com/salesiq/
2. Navigate to Bots → Create Bot
3. Select "Custom Script" option
4. Name: "Consulting Services Bot"
5. Go to Conversation Handler
6. Copy the code from `main.deluge` file
7. Add helper functions from `helpers.deluge`
8. Save the bot

## Step 2: Configure Google Calendar Integration

1. Go to https://console.cloud.google.com/
2. Create new project: "Cliqtrix Chatbot"
3. Enable Google Calendar API
4. Create OAuth 2.0 credentials:
   - Type: Web application
   - Authorized redirect URIs: `https://oauth.zoho.com/oauth`
5. Copy Client ID and Client Secret
6. In Zoho SalesIQ, create connection:
   - Name: `google_calendar_connection`
   - Type: OAuth 2.0
   - Paste credentials

## Step 3: Setup Twilio for OTP

1. Sign up at https://www.twilio.com/
2. Get Account SID and Auth Token
3. Assign Twilio phone number
4. In Zoho SalesIQ, create connection:
   - Name: `twilio_connection`
   - Type: Basic Auth
   - Username: Account SID
   - Password: Auth Token

## Step 4: Configure Email Service

1. Use Zoho Mail or SMTP
2. In `helpers.deluge`, update email sender address
3. Configure sendmail() function

## Step 5: Deploy Bot

1. Publish bot in SalesIQ Dashboard
2. Deploy to: Website, Mobile App, Facebook Messenger
3. Test with sample visitors
4. Verify email confirmations and OTP delivery

## Testing Checklist

- [ ] Book appointment flow
- [ ] OTP verification
- [ ] Calendar slot fetching
- [ ] Email confirmations
- [ ] Reschedule functionality
- [ ] Cancellation workflow
- [ ] Payment link generation

## Environment Variables

Store these securely:
```
GOOGLE_CLIENT_ID=your_client_id
GOOGLE_CLIENT_SECRET=your_secret
TWILIO_ACCOUNT_SID=your_sid
TWILIO_AUTH_TOKEN=your_token
TWILIO_PHONE=+1234567890
STRIPE_PUBLISHABLE_KEY=your_key
```

## Troubleshooting

**OTP not received:**
- Check Twilio credentials
- Verify phone number format (10 digits)
- Check Twilio account balance

**Calendar slots empty:**
- Verify Google OAuth token
- Check calendar permissions
- Ensure dates are in future

**Email not sending:**
- Verify SMTP settings
- Check recipient email validity
- Review email content

## Support

- Zoho SalesIQ: https://support.zoho.com/salesiq
- Google Calendar API: https://developers.google.com/calendar
- Twilio Docs: https://www.twilio.com/docs

## Submission

- Date: November 30, 2025
- Platform: Zoho SalesIQ
- Category: Chatbot (Consulting Services)
