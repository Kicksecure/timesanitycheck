# Checks if the system clock is sane between build timestamp and expiration date #

Reports, if clock is sane and not slower than build timestamp or faster than
expiration date (configurable, default currently set to 17 MAY 2033 10:00:00).

This should catch situations, where the host's clock is too much off (CMOS
battery defect, user mistakenly set a very wrong date, etc.), resulting in
network time synchronization tools (such as sdwdate) no longer being able to
correct the clock; catch eventual bigger bugs in network time synchronization
tools; and some types of attacks on network time synchronization.
## How to install `timesanitycheck` using apt-get ##

1\. Add [Whonix's Signing Key](https://www.whonix.org/wiki/Whonix_Signing_Key).

```
sudo apt-key --keyring /etc/apt/trusted.gpg.d/whonix.gpg adv --keyserver hkp://ipv4.pool.sks-keyservers.net:80 --recv-keys 916B8D99C38EAF5E8ADC7A2A8D66066A2EEACCDA
```

3\. Add Whonix's APT repository.

```
echo "deb http://deb.whonix.org buster main" | sudo tee /etc/apt/sources.list.d/whonix.list
```

4\. Update your package lists.

```
sudo apt-get update
```

5\. Install `timesanitycheck`.

```
sudo apt-get install timesanitycheck
```

## How to Build deb Package ##

Replace `apparmor-profile-torbrowser` with the actual name of this package with `timesanitycheck` and see [instructions](https://www.whonix.org/wiki/Dev/Build_Documentation/apparmor-profile-torbrowser).

## Contact ##

* [Free Forum Support](https://forums.whonix.org)
* [Professional Support](https://www.whonix.org/wiki/Professional_Support)

## Payments ##

`timesanitycheck` requires [payments](https://www.whonix.org/wiki/Payments) to stay alive!
