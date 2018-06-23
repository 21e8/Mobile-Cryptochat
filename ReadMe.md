# Mobile Cryptochat

This project is currently trying to create a mobile-friendly portable version of [Open Cryptochat](https://github.com/triestpa/Open-Cryptochat) which will eventually run on TOR.

So far there is:

- WIP: create a Cordova container
- WIP: Research on how to run NodeJS server from Android


# Wiki

## Mobile Server

### Get the tools

To get most things running on the Android phone we can use [Termux](https://termux.com/). 
- Install it from playstore
- Open, type
```
apt-get upgrade
pkg install vim-python 
pkg install tor 
pkg install torsocks
```

### Create a hidden service

For this to work you need all the tools installed. 
- `vim $PREFIX/etc/tor/torrc`
- uncomment and edit these lines (should be ln 72-73) by 
```
#HiddenServiceDir /usr/local/var/lib/tor/hidden_service/
#HiddenServicePort 80 127.0.0.1:80
```
=
- Save and quit
- run `tor`
- If successful, open new termux session
- `cat <HiddenServiceDir>/hostname` should outputt sth like this: `g3yv3tvqrbow7koz.onion`

References:
[Termux Remote Access](https://wiki.termux.com/wiki/Remote_Access#Installing_needed_packages)

