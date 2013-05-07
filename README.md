-------------------------------------------------------------------
[AttackVector Linux](http://attackvector.org): the dragon has tails
===================================================================
**AttackVector Linux** is a new distribution for anonymized penetration and security.  
It is based on [TAILS](https://tails.boum.org) and [Kali](http://kali.org), which are both based on [Debian](http://debian.org).

Design Philosophy
=================
**Yin** and _Yang_

While Kali requires a modified kernel for network drivers to use injection and so forth,  
TAILS is designed from the bottom up for encryption, and anonymity. _Nmap can't UDP via Tor._  
**The intention of AttackVector Linux is to provide the capability to anonymize attacks  
_while warning the user when he or she takes actions that may compromize anonymity._**  
The two projects have different design philosophies that can directly conflict with one another.  
In spite of this, the goal of **AttackVector Linux** is to integrate them complementarily into one OS.

##### Features
* The anonymity of [TAILS](https://tails.boum.org)
* The privacy of [SRWare Iron](http://www.srware.net/en/software_srware_iron.php)
* The cryptography of [DaKaRand](http://dankaminsky.com/2012/08/15/dakarand/)
* The penetration tools of [Kali](http://kali.org)

Build Instructions
==================
[ distro / build / kali_coms.txt ]

1. Install prerequisites in Kali:

    ~~~~~~
    apt-get install git live-build cdebootstrap kali-archive-keyring
    git clone git://git.kali.org/live-build-config.git
    apt-get remove libdebian-installer4
    apt-get install libdebian-installer4
    ~~~~~~

2. Copy down git repo [ distro / kali / config ]

    ~~~~~~
    git clone git://
    ~~~~~~

3. Live build:

    ~~~~~~
    lb clean --purge
    dpkg --add-architecture amd64
    lb config --architecture amd64 --mirror-binary http://http.kali.org/kali --mirror-binary-security http://security.kali.org/kali-security --apt-options "--force-yes --yes"
    lb build
    ~~~~~~

(Notice the similarity to [Kali Live-Build](http://docs.kali.org/live-build/live-build-a-custom-kali-iso).)

Download
========
[attackvector-linux_0.0.1alpha_64bit.iso](http://attackvector.org/attackvector-linux_0.0.1alpha_64bit.iso)

--------------
###### social
> IRC **#attackvector** on Freenode  
> [![Tweet This](http://ampedstatus.org/wp-content/plugins/tweet-this/icons/en/twitter/tt-twitter-micro4.png)](https://twitter.com/intent/tweet?text=%40attackvector)[![Facebook](http://daviddegraw.org/wp-content/plugins/tweet-this/icons/tt-facebook-micro4.png)](http://facebook.com/AttackVector-Linux)[![Linkedin](http://www.hollybrady.com/bradyholly/wp-content/plugins/tweet-this/icons/en/linkedin/tt-linkedin-micro4.png)](http://linkedin.com/in/AttackVector)  

##### Docs
* [Live Build Manual](http://live.debian.net/manual/3.x/html/live-manual/index.en.html)
* [TAILS git branches](https://tails.boum.org/contribute/git/#index4h3)
* How to [build TAILS](https://tails.boum.org/contribute/build/#index1h1)
* How to [customize TAILS](https://tails.boum.org/contribute/customize/#index1h1)
* [Rebuilding a Kali Package](http://docs.kali.org/development/rebuilding-a-package-from-source)
* [Rebuilding the Kali Kernel](http://docs.kali.org/development/recompiling-the-kali-linux-kernel)
* [Live Build a Custom Kali ISO](http://docs.kali.org/live-build/live-build-a-custom-kali-iso)
* How to [customize Debian live](http://live.debian.net/manual/current/html/live-manual/customizing-contents.en.html)

Project Status
==============

It seems our best structural approach is customizing the [Kali Live Build scripts](http://docs.kali.org/live-build/live-build-a-custom-kali-iso).  
Eventually this Kali derivative should meet the [TAILS design specifications](https://tails.boum.org/contribute/design/#index13h2).

##### Git
* [Kali git repositories](http://git.kali.org/gitweb/)
* [TAILS git repository](http://git.immerda.ch/?p=amnesia.git)
* [GitLab.org](http://gitlab.org) for hosting repos cron pull'd from the above (see **base-git-subtree.sh**)
* [GitLab-CI](https://github.com/gitlabhq/gitlab-ci#gitlab-ci-is-an-open-source-continuous-integration-server) Continuous Intergration system uses [Vagrant](http://vagrantup.com), just like [TAILS build](https://tails.boum.org/contribute/build/#index1h1) scripts
* Configure build system to generate & test ISOs

##### Tasks
* [Help port TAILS to Wheezy](https://tails.boum.org/todo/Wheezy/)
* Evaluate features of each distro & unify them into a single kernel
* Provide two layers of functionality: dedicated install and [live distro](http://www.irongeek.com/i.php?page=videos/portable-boot-devices-usb-cd-dvd)
* Add warning messages for anonymity risks
* Full Disk Encryption (FDE) w/ [LUKS](https://code.google.com/p/cryptsetup/)
* Host on [AttackVector.org](http://attackvector.org)
* Provide documentation
* [HTTPS Everywhere](https://www.eff.org/https-everywhere)
* Debian repositories

--------------
###### license
> [![Creative Commons License](http://i.creativecommons.org/l/by/3.0/80x15.png)](http://creativecommons.org/licenses/by/3.0/)[![Open Source](http://www.ipol.im/static/badges/open-source.png)](http://www.gnu.org/licenses/gpl.html)[![Hacker Emblem](http://catb.org/hacker-emblem/hacker.png)](http://www.catb.org/hacker-emblem/)  
> Text under [Creative Commons Attribution-NonCommercial-ShareAlike 3.0 Unported License](http://creativecommons.org/licenses/by-nc-sa/3.0/). Code under [GNU Public License](http://www.gnu.org/licenses/gpl.html). © Kenneth Soona 2013