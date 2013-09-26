# Nginx Proxy to Cloudant

This is the config we use to talk to Cloudant without changing any of our
existing services.

It requires two things - the hostname and the Basic Auth header and then
it is good to go. To generate the basic auth:

`echo "username:password" | openssl enc -base64`

Then pop that in set header Authorization following the word Basic. That's it.

Tested with nginx 1.1.19.

## Why?

We figured this might be useful to others who migrate from CouchDB to Cloudant
