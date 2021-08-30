# api-specs
Describes the API interface for AppFeedback for your own implementations

Register for an account here: https://my.appfeedback.io/sign-up

We currently have two POST APIs available, Simple & Multipart

Multipart is only required if you want to upload logs/images/binary files to AppFeedback, otherwise the Simple API is the best to get started.


# Simple API

POST JSON Data to:
https://api.appfeedback.io/v2/feedback-simple/

Json Layout:
```javascript
{
    "project_key": "YOUR_PROJECT_KEY_HERE",
    "feedback": "Your feedback string here",
    "email": "email@email.com",
    "happiness": 10,
    "version": "1.0.0",
    "additional_data": {        
        "anything_you_want":"nice",
        "tag": "Bug"
    }
}
```
Bare minimum you must send the project_key, but of course you should add feedback etc to make the most!
additional_data is just for anything else you want to add

# Multipart API

More advanced API which supports uploading logs/images/binary files

Ensure the POST is a multipart/form-data request

Name | Type | Required | Info
-----|------|----------|-----
afjson|Raw String|YES|This needs to be laid out in same format as the Simple API
aflog|Raw String|NO|
afbin|Raw Binary|NO|
afimg|Raw Binary|NO| Only JPG or PNG Encodings Supported

https://api.appfeedback.io/v2/feedback-multipart/
