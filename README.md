# Checks if the system clock is sane between build timestamp and expiration date #

Reports, if clock is sane and not slower than build timestamp or faster than
expiration date (configurable, default currently set to 17 MAY 2033 10:00:00).

This should catch situations, where the host's clock is too much off (CMOS
battery defect, user mistakenly set a very wrong date, etc.), resulting in
network time synchronization tools (such as sdwdate) no longer being able to
correct the clock; catch eventual bigger bugs in network time synchronization
tools; and some types of attacks on network time synchronization.

## How to install `timesanitycheck` using apt-get ##

1\. Download the APT Signing Key.

```
wget https://www.kicksecure.com/keys/derivative.asc
```

Users can [check the Signing Key](https://www.kicksecure.com/wiki/Signing_Key) for better security.

2\. Add the APT Signing Key.

```
sudo cp ~/derivative.asc /usr/share/keyrings/derivative.asc
```

3\. Add the derivative repository.

```
echo "deb [signed-by=/usr/share/keyrings/derivative.asc] https://deb.kicksecure.com trixie main contrib non-free" | sudo tee /etc/apt/sources.list.d/derivative.list
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

See instructions.

NOTE: Replace `generic-package` with the actual name of this package `timesanitycheck`.

* **A)** [easy](https://www.kicksecure.com/wiki/Dev/Build_Documentation/generic-package/easy), _OR_
* **B)** [including verifying software signatures](https://www.kicksecure.com/wiki/Dev/Build_Documentation/generic-package)

## Contact ##

* [Free Forum Support](https://forums.kicksecure.com)
* [Premium Support](https://www.kicksecure.com/wiki/Premium_Support)

## Donate ##

`timesanitycheck` requires [donations](https://www.kicksecure.com/wiki/Donate) to stay alive!
