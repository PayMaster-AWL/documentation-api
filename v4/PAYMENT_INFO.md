### Status code
- PAYMENT_CANCELED - Payment has been canceled
- PAYMENT_SUCCESSFUL - Payment was successful
- PAYMENT_UNDEFINED - Unidentified error

### PAYMENTMETHOD
- VISAMASTER - to pay with a card

### List of currencies and supported payment methods
* USD - VISAMASTER

## Email config
This is the configuration object for sending emails.

If you want us to send emails, set all values to true.

This is the object :
```json
{
  emailToClient: boolean,
  emailToMerchant: boolean
}
```

## Language
Supported language:
* fr
* en

## Phone
Supported format: 79999999999
If you send the phone 79662002724, then your phone will look like +79662002724

If you enter a phone number starting with +, then your phone field will be invalidated
