# Caprover Cli Simple PHP Deploy

### Instructions to deploy this simple application at localhost:

`caprover serversetup`
```
? have you already started CapRover container on your server? Yes
? IP address of your server: 127.0.0.1
? current CapRover password: [hidden]
? CapRover server root domain:
```

`caprover login`
```
Login to a CapRover machine...

? CapRover machine URL address, it is "[http[s]://][captain.]your-captain-root.domain": http://captain.captain.localhost
? CapRover machine password: [hidden]
? CapRover machine name, with whom the login credentials are stored locally: captain-01
```

- Create an empty app in Caprover GUI

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

Some useful links:
https://github.com/caprover/caprover-cli
https://caprover.com/docs/captain-definition-file.html
