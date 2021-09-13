## Getting 500 error
With [[Domain Configurations#Alva Serivces]] we cannot use staging, sandbox, or the prod domain. To continue on this we must deploy to prod but first need sandbox. This is all for formality.

### Release EJS Server
This is needed for the frontend for the ml-patient-record-sychronization service to be deployed with the backend interop stuff.

#### *Release for Prod has been completed*
System testing is needed, to test endpoints look for a 404 or 500 error when on the s1941 domain (see [[Domain Configurations#Alva Serivces]] for reason). Must be connect to CernerWorks vpn in order to test properly