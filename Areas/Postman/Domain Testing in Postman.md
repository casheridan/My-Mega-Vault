## How to test on a specific service in Postman for Cerner Corprate domains (dev)
1. Pull up a new request in postman
2. Go to the Authorization tab and select OAuth 1.0, refer to [[Generate a OAuth 1.0 Token]] for more info if domain cannot generate a OAuth token.
3. Generate a new token, follow steps 2-4 in [[Generate a OAuth 1.0 Token#How to Generate an OAuth 1 0 Token]].
4. Find a valid patient and copy their patient id
5. insert it via {service directory url}/service/patients/{patient id}/{service name}

## How to test on a specific service in Postman for CernerWorks domains (staging, sandbox, prod)
---
1. Pull up a new request in postman
2. Go to the Authorization tab and select OAuth 1.0, refer to [[Generate a OAuth 1.0 Token]] for more info if domain cannot generate a OAuth token.
3. Generate a new token, follow steps 2-4 in [[Generate a OAuth 1.0 Token#How to Generate an OAuth 1 0 Token]].
4. Find the URL for the domain and service in the [Service Directory](https://directory.careaware.com/services-directory/)
5. Find a valid patient and copy their patient id
6. insert it via {service directory url}/service/patients/{patient id}/{service name}

TOC