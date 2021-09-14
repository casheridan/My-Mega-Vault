## Why we can't generate a OAuth token
---
We couldn't generate a token in the OAuth Token Generator 1.0 for our environment because there weren't the right variables in the environment to begin with


## How to Generate an OAuth 1.0 Token
---
To generate a new token for a new domain you must first copy and import the domain environment from the [cpoe-manual-testing-resources](https://github.cerner.com/orders-plans/cpoe-manual-testing-resources) into Postman. Then follow these steps

1. Add the following to the environment variables
	* username
	* password
	* domain
		* *this is the url for the domain ex: 64dev.ip.devcerner.net although cpoe-manual-testing-resources usually already have a domain in the environment*
		

> sometimes username and password can be as simple as *system*

2. Open a new Runner tab (you can find this in "Files")
3. Drag in the "Oauth Token Generator v1.0"
	* Make sure you have your domain selected in the top right*
4. Click "Start Run"
5. Check in the variables of the environment and see if the oauth_token and oauth_token_secret were generated
6. If they are continue to testing [[Domain Testing in Postman]]
