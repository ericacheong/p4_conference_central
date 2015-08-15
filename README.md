#P4: Conference Organization App

This project is part of the Udacity: Full Stack Web Developer Nanodegree.

The Conference Organization App uses a cloud-based API server to support a provided conference organization application that exists on the web as well as a native Android application. The API supports the following functionality found within the app: user authentication, user profiles, conference information and various manners in which to query the data.

##Task 1: Add Sessions to a Conference
In Session model, speakers is implemented as list of strings. Multiple speakers for a session is allowed.

In Session model, 'name', 'highlights', 'speakers', 'typeOfSession' are implemented as StringProperty because they are simple strings. 'duration' is implemented as IntegerProperty so that the length of session can be compared. 'date' and 'startTime' are implemented as DateProperty and TimeProperty respectively to reflect their usage. 

##Task 2: Add sessions to user wishlist
Wishlist is implemented as part of Profile. It stores a list of session keys. 


##Task 3: Work on indexes and queries
A general query endpoint for multiple queries is implemented. It supports query by name, speakers, duration, typeOfSession, date and startTime.

The query problem has two inequality filters applied to two properties. Google datastore API restricts an inequality filter can be applied to at most one property. Two queries are constructed and the final result is constructed in Python.


##Task 4: Add a Task
When a new session is added, the speaker is checked if multiple sessions are held by this speaker. A new memcache entry is added with the session names.

getFeaturedSpeaker endpoint returns all speakers and the session names in memcache.    

## Products
- [App Engine][1]

## Language
- [Python][2]

## APIs
- [Google Cloud Endpoints][3]

## Setup Instructions
1. Update the value of `application` in `app.yaml` to the app ID you
   have registered in the App Engine admin console and would like to use to host
   your instance of this sample.
1. Update the values at the top of `settings.py` to
   reflect the respective client IDs you have registered in the
   [Developer Console][4].
1. Update the value of CLIENT_ID in `static/js/app.js` to the Web client ID
1. (Optional) Mark the configuration files as unchanged as follows:
   `$ git update-index --assume-unchanged app.yaml settings.py static/js/app.js`
1. Run the app with the devserver using `dev_appserver.py DIR`, and ensure it's running by visiting your local server's address (by default [localhost:8080][5].)
1. (Optional) Generate your client library(ies) with [the endpoints tool][6].
1. Deploy your application.


[1]: https://developers.google.com/appengine
[2]: http://python.org
[3]: https://developers.google.com/appengine/docs/python/endpoints/
[4]: https://console.developers.google.com/
[5]: https://localhost:8080/
[6]: https://developers.google.com/appengine/docs/python/endpoints/endpoints_tool
