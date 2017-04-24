# Shairplay Sync on the Omega

The code in this repo is the default UCI configuration file on a fresh installation of shairport-sync on the Omega2/2+. Reverting any changes you've made can be done by copying the `etc/config/shairport-sync` file to the `/etc/config/` directory in your omega, replacing the file of the same name.


## Setting it up

To set up shairplay-sync on the omega, 

```
opkg remove avahi-nodbus-daemon --force-depends
opkg update
opkg install avahi-dbus-daemon --force-overwrite
opkg install shairport-sync
```

To configure it correctly, ensure the following options are edited as below:

```
        option disabled '0'
        option name 'your-device-name'
        option password 'your-password'
        option mdns_backend 'tinysvcmdns'
```

Reboot, then run it with the `-d` flag:

```
shairport-sync -d
```

