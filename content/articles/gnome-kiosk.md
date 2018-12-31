---
title: "Linux as a kiosk: automatic log-ins with GNOME"
date: 2018-12-31T11:28:02Z
---

Home entertainment systems and public kiosks are often required to boot up without human interference, so they can be
set-up quickly after being moved to a different physical location, or survive power outages. Due to their public nature,
different people use the same system user, which must be logged in automatically. To set this up, we must tell Linux two
things: which user to log in by default, and that this user does not require any authentication.

## Restrict user privileges
First, create or choose the user you want the public to use. **Because everybody and anybody will have access to this
user, it must not have more privileges than absolutely necessary.** It's often a good idea to create a completely new
user, so group memberships and permissions can be tailored to the few tasks the public must be able to perform.

## Automatic log-in
We need to tell the display manager it must log in this user automatically. This requires a small change to a
configuration file. Ensure `/etc/gdm3/custom.conf` contains the following two lines, where `bart` must be replaced with
the name of your unprivileged user:
```
AutomaticLoginEnable = true
AutomaticLogin = bart
```

## Passwordless authentication
We have told Linux which user to log in automatically, but this will still require a password when resuming an existing
log-in session after the screen has gone blank or the machine has been suspended. We'll use a
[PAM](https://en.wikipedia.org/wiki/Linux_PAM) [config file](https://linux.die.net/man/5/pam.d) to tell Linux our user
requires no authentication at all. Edit `/etc/pam.d/gdm-password` and put the following line at the beginning of the
file, where `bart` must again be replaced with the name of your unprivileged user:
```
auth sufficient pam_succeed_if.so user = bart
```
Whenever Linux tries to *authenticate* a user called `bart`, that is *sufficient*, and no other steps, such as a
password, are necessary. This effectively disables any authentication for this user.

## Conclusion
Now your machine can be rebooted, and you should see it go straight to your unprivileged user's desktop! 