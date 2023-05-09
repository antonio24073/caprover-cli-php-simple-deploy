# Caprover Cli Simple Deploy

### Instructions to deploy this simple caprover application with cli at localhost
It's not an official documentation

----------
install:

`npm install -g caprover`

----------
`caprover serversetup`
```
? have you already started CapRover container on your server? Yes
? IP address of your server: 127.0.0.1
? current CapRover password: [hidden]
? CapRover server root domain:
```
----------
`caprover login`
```
Login to a CapRover machine...

? CapRover machine URL address, it is "[http[s]://][captain.]your-captain-root.domain": http://captain.captain.localhost
? CapRover machine password: [hidden]
? CapRover machine name, with whom the login credentials are stored locally: captain-01
```
-----------

Create an app:

`
caprover api -n captain-01 -m POST  -t /user/apps/appDefinitions/register -d {\"appName\":\"aaa\"}
`

When use the api, don't forgot to remove /api/v2 from path

-----------
`caprover deploy`

```
Preparing deployment to CapRover...

**** Protip ****
You seem to have deployed aaa from this directory in the past, use --default flag to avoid having to re-enter the information.

? select the CapRover machine name you want to deploy to: captain-01
Ensuring authentication...
? select the app name you want to deploy to: aaa
? git branch name to be deployed: main
? note that uncommitted and gitignored files (if any) will not be pushed to server! Are you sure you want to deploy? Yes
```
-------------
Expected response:

```
Deploying aaa to captain-01...

Uploading [====================] 100%  (ETA 0.0s)
Upload done.

This might take several minutes. PLEASE BE PATIENT...

Building your source code...

------------------------- Mon Mar 27 2023 20:39:32 GMT+0000 (Coordinated Universal Time)
Build started for aaa
Ignore warnings for unconsumed build-args if there is any
Step 1/2 : FROM library/php:7.2-apache

---> c61d277263e1
Step 2/2 : COPY ./ /var/www/html/

---> Using cache
---> 99f36d84f7ca
[Warning] One or more build-args [CAPROVER_GIT_COMMIT_SHA] were not consumed
Successfully built 99f36d84f7ca
Successfully tagged img-captain-aaa:latest
Build has finished successfully!

Deployed successfully aaa
App is available at http://aaa.captain.localhost
```


----------
Some useful links:
- https://github.com/caprover/caprover-cli
- https://caprover.com/docs/captain-definition-file.html


------------------------------

# Donations

Help keep projects free:

https://www.paypal.com/donate/?business=X3W3QTHS7BDW4&no_recurring=0&item_name=Help+me+to+continue+the+free+projects&currency_code=BRL
