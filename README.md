## Google Calendar API OAuth 2.0 for Web Server Applications Integration - Django Rest Framework

Setup Virtual Env

```
# Create a virtual environment to isolate our package dependencies locally
python3 -m venv env
source env/bin/activate  # On Windows use `env\Scripts\activate`
```

For run this project on a local machine:

```sh
pip install -r requirements.txt
python manage.py runserver
```

- Endpoint:

http://127.0.0.1:8000/rest/v1/calendar/init/

```
/rest/v1/calendar/init/ -> GoogleCalendarInitView()
```

This view should start step 1 of the OAuth. Which will prompt user for his/her credentials

```
/rest/v1/calendar/redirect/ -> GoogleCalendarRedirectView()
```

This view will do two things

1. Handle redirect request sent by google with code for token. You
   need to implement mechanism to get access_token from given
   code
2. Once got the access_token get list of events in users calendar

### Note: Configuration.

Download Oauth Client File & Rename as credentials.json

![](screenshot/Oauth_Client_Setup.png?raw=true)

### Output

![](screenshot/OutPut.png?raw=true)

## Documents and References

| Name                                                         | Sources                                                                   |
| ------------------------------------------------------------ | ------------------------------------------------------------------------- |
| Google Identity: Using OAuth 2.0 for Web Server Applications | [/identity/protocols/oauth2/web-server][PlDb]                             |
| Google Calendar API                                          | [/calendar/api/v3/referenc][PlGh]                                         |
| Google Account Credentials                                   | [/identity/protocols/oauth2/web-server#exchange-authorization-code][PlIa] |

[PlDb]: https://developers.google.com/identity/protocols/oauth2/web-server
[PlGh]: https://developers.google.com/calendar/api/v3/reference
[PlIa]: https://developers.google.com/identity/protocols/oauth2/web-server#exchange-authorization-codee
