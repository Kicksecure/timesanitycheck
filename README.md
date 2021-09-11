# Checks if the system clock is sane between build timestamp and expiration date #

Reports, if clock is sane and not slower than build timestamp or faster than
expiration date (configurable, default currently set to 17 MAY 2033 10:00:00).

This should catch situations, where the host's clock is too much off (CMOS
battery defect, user mistakenly set a very wrong date, etc.), resulting in
network time synchronization tools (such as sdwdate) no longer being able to
correct the clock; catch eventual bigger bugs in network time synchronization
tools; and some types of attacks on network time synchronization.
## How to install `timesanitycheck` using apt-get ##

1\. Download Whonix's Signing Key.

```
wget https://www.whonix.org/patrick.asc
```

Users can [check Whonix Signing Key](https://www.whonix.org/wiki/Whonix_Signing_Key) for better security.

2\. Add Whonix's signing key.

```
sudo cp ~/derivative.asc /usr/share/keyrings/derivative.asc
```

3\. Add Whonix's APT repository.

```
echo "deb [signed-by=/usr/share/keyrings/derivative.asc] https://deb.whonix.org bullseye main contrib non-free" | sudo tee /etc/apt/sources.list.d/derivative.list
```

4\. Update your package lists.

```
sudo apt-get update
```

5\. Install `timesanitycheck`.

```
sudo apt-get install timesanitycheck
```

## How to Build deb Package from Source Code ##

Can be build using standard Debian package build tools such as:

```
dpkg-buildpackage -b
```

See instructions. (Replace `generic-package` with the actual name of this package `timesanitycheck`.)

* **A)** [easy](https://www.whonix.org/wiki/Dev/Build_Documentation/generic-package/easy), _OR_
* **B)** [including verifying software signatures](https://www.whonix.org/wiki/Dev/Build_Documentation/generic-package)

## Contact ##

* [Free Forum Support](https://forums.whonix.org)
* [Professional Support](https://www.whonix.org/wiki/Professional_Support)

## Donate ##

`timesanitycheck` requires [donations](https://www.whonix.org/wiki/Donate) to stay alive!
