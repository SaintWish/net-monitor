# net-monitor
Prometheus and Grafana internet monitor Docker stack made for personal use.

## Notice
I modified this for my personal needs to run on my Raspberry Pi 3B, so use this at your own risk. It is also recommended that you know what you're doing before attempting to use this project.

## Quick Start
```
git clone https://github.com/geerlingguy/internet-monitoring
cd internet-monitoring
docker-compose up -d
```

Go to [http://localhost:3030/d/o9mIe_Aik/internet-connection](http://localhost:3030/d/o9mIe_Aik/internet-connection) (change `localhost` to your docker host ip/name).

## Known Issues
On the Raspberry Pi 3B running `Raspbian 10 (buster)` if you get a similar error to this:
``
speedtest_1   | Fatal Python error: init_interp_main: can't initialize time
speedtest_1   | Python runtime state: core initialized
speedtest_1   | PermissionError: [Errno 1] Operation not permitted
``

You need to get a updated `libseccomp2` package. Which you can do by typing this in.
``
wget http://ftp.us.debian.org/debian/pool/main/libs/libseccomp/libseccomp2_2.5.1-1_armhf.deb && sudo dpkg -i libseccomp2_2.5.1-1_armhf.deb
``

## Credits
* Thanks to @geerlingguy because this entire thing is based off his [internet monitor](https://github.com/geerlingguy/internet-pi)
* Thanks to @maxandersen for making the [original project](https://github.com/maxandersen/internet-monitoring) this fork is based on.
* Thanks to @vegasbrianc work on making a [super easy docker](https://github.com/vegasbrianc/github-monitoring) stack for running prometheus and grafana.
