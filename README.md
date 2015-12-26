# SmsAlexa
Implementation of wrapper code to enable sending sms text messages using the Amazon Echo (Alexa) and the Twilio REST Api.

# Keywords 
Amazon, Alexa, Echo, Twilio, Rest, AWS, Lambda, Alexa Skill Kit, ASK

# Description
 SmsAlexa is the implementation of an Amazon AWS Lambda function which enables sending of SMS text messages via voice.

 Steps : 
  
 1. You need to create a Twilio account. once you have one, you can get a free phone number for your country. I live in Germany, which is why the phone numbers in this example are preceded by +49. Make sure the phone number you get at Twilio supports sms.
 2. In your Twilio account settings, you need to find out the account session Id and authentification token. You will need them in the next stage when creating your lambda function.
 3. If you don't already have one, get an Amazon AWS account (free). 
 4. From the AWS Console, you need to create a Lambda function wich will execute the code that will send the sms text decoded from speach to the sms gateway.
 5. Give the lambda function a name and a default operating role.
 6. Paste in the code from SmsAlexa_AWSLambda.js found in this repository. fill in your Twilio credentials in this lambda function, namely your session id and auth token.
 7. Take the ARN id of your lambda function (found on the top right of the lambda), you will need it in the next stage when creating an Alexa skill
 8. You need to create a new Alexa skill from https://developer.amazon.com/edw/home.html#/skills/list using the Alexa Skill Kit (ASK)
 9. Give the skill a name, I chose "sms" and choose the endpoint to be your previously implemented lambda function. Paste in your ARN id.
 10. In the interaction model, type in the intent schema presented in interactionModel_intentSchema.json in this repository
 11. In the Sample Utterances fill in the content of sampleUtterances.txt
 12. You can Skip Test and Publishing information for now. Your skill should be ready.
 
# Usage
I use it like : "Alexa, open sms and send my wife {text}". The request automatically calls the lambda function described above which in turn calls the Twilio api with the parsed text from speech. Wife is happy for having received an sms. 
 
# License
This software is freely available under the GNU GPL v3.0 aegis, please consult the LICENSE file for further information
