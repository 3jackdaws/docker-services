# Email & Stuff
A Single Container to do all email stuff including postfix, dovecot, opendkim, opendmarc, and so on.  I know this is in violation of Docker philosophy, but it doesn't pollute your management software with 18 containers just to facilitate email.

## Contents

### docker-compose.yml
Gets ENV parameters from the .env file.

### .env
Set variables in here.

### setup.sh
Used to manage email users and aliases.


[Additional Information](https://github.com/tomav/docker-mailserver)