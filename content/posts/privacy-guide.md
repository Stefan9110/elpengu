---
title: "Online Privacy Guide"
date: 2022-12-08T09:41:23+02:00
showTitle: true
draft: true
toc: false
images:
tags:

- open-source
- privacy

---

One benefit of using [libre software](../why-libre-software/) is the privacy
you're getting. Libre software usually contains **no spyware**, **no trackers**
and **no ads**, because if it did, it could be easily pointed out in the source
code **and removed by forking the project**.

The same can't be said about closed-source software, because, not being able to
audit the source code, its privacy is as good as the developer promises. There
have been many cases of software **lying about it's data collection**, or
hiding it deep inside their terms of service.

Thus, the first step to have a more private internet experience is using libre
software only. However, even with libre software, there are some additional
steps required to ensure better privacy.

# Identifying a threat model

{{< image src="/images/pepe-paranoid.webp" position="right" style="width: 40%; margin: 15px" >}}

You cannot have both **privacy** and **convenience**. There is always a tradeoff
between the two. For this reason it is important to establish a personal threat
model you want to protect against, to know how far to go. The goal should be
obtaining a balance between the two, not going all out on one.

## Possible threat models

1. Strangers
2. Family, friends
3. Stalkers
4. Companies
5. Governments
6. **Everyone**

The higher on the list, the higher privacy you should seek. This guide will help
you improve only your online privacy. If you set a thread model between the
last two, you should also look into hardware privacy, such as [libre boot](https://libreboot.org/)
and [degoogled Android phone](https://grapheneos.org/).

# {{< color "Step 1" "#D092FC" >}} ➤ Browser

The browser is the program you use the most, so it makes sense to secure it.
There are a few things to look out for in a good browser:

* Provides a way to disable **javascript**
* Is **open-source**
* Does not phone home (or provides a way to disable phoning home)
* Does not connect to any unsolicited IPs

Knowing this, we can definetely say that the following browsers are a threat
for your privacy: **Google Chrome**, **Opera**, **Safari**, **Microsoft Edge**.

## Good practices

1. Clear your cache everytime you close your browser
2. Use only non-javascript website when possible
3. Spoof your **user agent** to fit in with the others. Make sure you [are not unique](https://amiunique.org/fpNoJS)
4. Use privacy-friendly alternatives for popular websites (see the guide below)
5. Only use HTTPS
6. Check what connections your browser is making, with a tool such as **iftop**

There are a few browsers out there that provide good privacy, while also having
modern features. I will rank them based on the privacy they provide outside the
box. You should choose a browser based on your threat model, needs and
experience with tinkering with configurations.

## Browser list

[//]: # (Firefox)
<details class="post-box">
<summary class="post-box-title">
<img class='box-logo' src="/images/firefox.webp">
<h2>Firefox</h2>
<p class="box-privacy">{{< text-icon privacy "#FF5555" >}} Privacy Level: <b><span style="color: #FF5555">Low</span></b></p>
</summary>
<hr>

**Firefox** is the default browser on **most Linux distributions**. This makes it
a solid option for new users and people just beginning their privacy journey.
Although {{< color "not a good solution" "#FF5555" >}} in the long run, Firefox provides an indispensable
basis for other browsers, being a direct competitor to Chromium.

Firefox phones home by default and has javascript enabled. Firefox can have a
**decent** privacy level if applying [arkenfox's
user.js](https://github.com/arkenfox/user.js/) and installing
privacy extensions. A simple and efficient guide for hardening Firefox can be
found [here](https://spyware.neocities.org/guides/firefox.html).

If you are not willing to configure Firefox, you should look into its forks that provide better privacy defaults.

<span class="i-blog">
<a style='margin-right: 10px' href="https://www.mozilla.org/en-US/firefox/new/">[Download]</a>
<a href="https://www.mozilla.org/">[Website]</a>
</span>
</details>

[//]: # (Librewolf)
<details class="post-box">
<summary class="post-box-title">
<img class='box-logo' src="/logos/librewolf.svg">
<h2>Librewolf</h2>
<p class="box-privacy">{{< text-icon privacy "#FFAA00" >}} Privacy Level: <b><span style="color: #FFAA00">Medium</span></b></p>
</summary>
<hr>

**Librewolf** is a fork of Firefox aiming to fix all of its parent's problems. It
hardens Firefox and ships **uBlock Origin** by default, a powerful ad blocking and
javascript blocking tool.

Librewolf phones home at startup, although it can be disabled from
**about:config**. If all you want is a browser that works, Librewolf is the
middle ground for privacy and convenience. Definitely use over vanilla Firefox.

<span class="i-blog">
<a style='margin-right: 10px' href="https://librewolf.net/installation/">[Download]</a>
<a href="https://librewolf.net/">[Website]</a>
</span>
</details>

[//]: # (Tor Browser)
<details class="post-box">
<summary class="post-box-title">
<img class='box-logo' src="/logos/tor-browser.svg">
<h2>Tor Browser</h2>
<p class="box-privacy">{{< text-icon privacy "#00AA00" >}} Privacy Level: <b><span style="color: #00AA00">High</span></b></p>
</summary>
<hr>

**TOR Browser** is a fork of Firefox built to be used on the onion network. Depending on your threat model, you might
need to use the onion router to access certain websites. Tor is the recommended browser for doing so in order to blend
in with other tor users.

TOR Browser **does NOT have** the best privacy settings outside the box. Javascript is enabled by default, and you
**absolutely don't want to use that** on onion websites. You also don't want to use DuckDuckGo, the default search
engine. Not only it does not index onion sites, but it is also not good for your privacy. Use a privacy respecting
search engine instead (see below).

To disable JS, go into settings and select the **Safest** option from Privacy & Security.

Note that TOR might be blocked on your network / in your country. In that case, you need to use a **TOR bridge** to
connect to the onion network.

<span class="i-blog">
<a style='margin-right: 10px' href="https://www.torproject.org/download/">[Download]</a>
<a href="https://www.torproject.org/">[Website]</a>
</span>
</details>

[//]: # (IceCat)
<details class="post-box">
<summary class="post-box-title">
<img class='box-logo' src="/logos/icecat.svg">
<h2>GNU IceCat</h2>
<p class="box-privacy">{{< text-icon privacy "#55FF55" >}} Privacy Level: <b><span style="color: #55FF55">Very High</span></b></p>
</summary>
<hr>

**IceCat** is GNU's fork of Firefox. It is the best Firefox alternative because
it provides the most privacy features, however they come at the cost of
usability. IceCat is known for easily breaking website due to its **LibreJS** feature.

It is a good option if you need to browse the internet safely and don't care
about some sites that require javascript not working. If your thread model is
high enough you shouldn't use websites that require javascript anyway.

IceCat can be used to connect to the onion network, however that is not recommended due to your unique fingerprint
related to using another browser than **TOR**.

<span class="i-blog">
<a href="https://www.gnu.org/software/gnuzilla/">[Website & Download]</a>
</span>
</details>

[//]: # (Brave)
<details class="post-box">
<summary class="post-box-title">
<img class='box-logo' src="/logos/brave.svg">
<h2>Brave</h2>
<p class="box-privacy">{{< text-icon privacy "#FFAA00" >}} Privacy Level: <b><span style="color: #FFAA00">Medium</span></b></p>
</summary>
<hr>

**Brave** is the browser based on Chromium that advertised itself as **the**
browser for privacy. It comes with good privacy features outside the box,
however it is known for adding spyware features in the past, such as
**telemetry**, **auto-updates** and **Brave Rewards**.

Should only be used if Chromium engine is required and Ungoogled Chromium cannot be
compiled in a reasonable amount of time, or the binary cannot be installed, for some reason.

Brave can be used to connect to the onion network, however that is not recommended due to your unique fingerprint
related to using another browser than **TOR**. Moreover, its suspicious privacy features make it a bad tool to browse
onion websites.

<span class="i-blog">
<a style='margin-right: 10px' href="https://brave.com/download/">[Download]</a>
<a href="https://brave.com/">[Website]</a>
</span>
</details>


[//]: # (Ungoogled Chromium)
<details class="post-box">
<summary class="post-box-title">
<img class='box-logo' src="/logos/chromium.svg">
<h2 style="font-size: 32px">Ungoogled Chromium</h2>
<p class="box-privacy">{{< text-icon privacy "#00AA00" >}} Privacy Level: <b><span style="color: #00AA00">High</span></b></p>
</summary>
<hr>

**Ungoogled Chromium** is Google Chrome without **trackers**, **ads**,
**phoning home**, **Google search engine**, **Google Extension Store**,
**Google accounts**. Therefore, it is very minimal and does not provide any
privacy features out of the box.

Its downside is that you have to compile it and it is not user-friendly,
installing extensions being a tedious task. However, if you need a chromium
based browser, it is the best solution out there.

<span class="i-blog">
<a href="https://github.com/ungoogled-software/ungoogled-chromium">[Download & Website]</a>
</span>
</details>

##

# {{< color "Step 2" "#D092FC" >}} ➤ Privacy-friendly online services

Even if you have a secure browser, your data is still accessible if you **simply
hand it over** to Google, Facebook or other companies. You should aim to
replace **all of your services** from these companies with privacy-friendly
alternatives.

You can see the privacy-friendly services hosted by **ElPengu** [here](../../services).

## Search Engines

[//]: # (LibreX)
<details class="post-box">
<summary class="post-box-title">
<img class='box-logo' src="/logos/librex.png">
<h2 style="font-size: 32px">LibreX</h2>
<p class="box-privacy">{{< text-icon privacy "#55FF55" >}} Privacy Level: <b><span style="color: #55FF55">Very High</span></b></p>
</summary>
<hr>

{{< image src="/images/librex-interface.webp" position="center" style="width: 100%; border:1px solid #4e4e57;" >}}

**LibreX** is a meta search engine that pulls Google results. It uses **no
javascript**, therefore your search queries can't be tracked.

LibreX is written in php, therefore it is lightweight and can be easily hosted by anyone.

Useful features LibreX includes:

* Torrent search
* Onion links indexes
* Custom searches such as crypto converting
* **Configurable** privacy-friendly instance URL replacer

<span class="i-blog">
<a style='margin-right: 10px' href="https://librex.beparanoid.de">[Recommended Instance]</a>
<a style='margin-right: 10px' href="https://github.com/hnhx/librex#instances">[Instance List]</a>
<a style='margin-right: 10px' href="https://github.com/hnhx/librex">[Source]</a>
</span>
</details>

[//]: # (SearXNG)
<details class="post-box">
<summary class="post-box-title">
<img class='box-logo' src="/logos/searx.png">
<h2 style="font-size: 32px">SearXNG</h2>
<p class="box-privacy">{{< text-icon privacy "#00FF11" >}} Privacy Level: <b><span style="color: #00FF11">High</span></b></p>
</summary>
<hr>

{{< image src="/images/searxng-interface.webp" position="center" style="width: 100%; border:1px solid #4e4e57;" >}}

**SearXNG** is a fork of SearX, a meta search engine that pulls results from
**a lot** of search engines, including Google, DuckDuckGo, StartPage. It
requires javascript for proper use, which can be maliciously modified by the
host, but has the advantage of being **very** customizable.

Features:

* Torrent search
* Vim keys
* Tracker URL remover
* Special queries

<span class="i-blog">
<a style='margin-right: 10px' href="https://searx.elpengu.com">[Recommended Instance]</a>
<a style='margin-right: 10px' href="https://searx.space/">[Instance List]</a>
<a style='margin-right: 10px' href="https://github.com/searxng/searxng">[Source]</a>
</span>
</details>

[//]: # (Whoogle)
<details class="post-box">
<summary class="post-box-title">
<img class='box-logo' src="/logos/whoogle.webp">
<h2 style="font-size: 32px">Whoogle</h2>
<p class="box-privacy">{{< text-icon privacy "#00FF11" >}} Privacy Level: <b><span style="color: #00FF11">High</span></b></p>
</summary>
<hr>

{{< image src="/images/whoogle-interface.webp" position="center" style="width: 100%; border:1px solid #4e4e57;" >}}

**Whoogle** is a customizable search engine pulling results from Google. It doesn't require javascript and is
lightweight on the system. It is written in python, therefore it can be slow at times depending on server load. Can be
easily deployed locally.

Features:
* Tracker URL remover
* Randomly generated user agent
* Proxy support

<span class="i-blog">
<a style='margin-right: 10px' href="https://search.albony.xyz">[Recommended Instance]</a>
<a style='margin-right: 10px' href="https://github.com/benbusby/whoogle-search#public-instances">[Instance List]</a>
<a style='margin-right: 10px' href="https://github.com/benbusby/whoogle-search">[Source]</a>
</span>
</details>

## YouTube alternatives
[//]: # (Invidious)
<details class="post-box">
<summary class="post-box-title">
<img class='box-logo' src="/logos/invidious.png">
<h2 style="font-size: 32px">Invidious</h2>
<p class="box-privacy">{{< text-icon privacy "#55FF55" >}} Privacy Level: <b><span style="color: #55FF55">Very High</span></b></p>
</summary>
<hr>

{{< image src="/images/whoogle-interface.webp" position="center" style="width: 100%; border:1px solid #4e4e57;" >}}

Descr

<span class="i-blog">
<a style='margin-right: 10px' href="https://search.albony.xyz">[Recommended Instance]</a>
<a style='margin-right: 10px' href="https://github.com/benbusby/whoogle-search#public-instances">[Instance List]</a>
<a style='margin-right: 10px' href="https://github.com/benbusby/whoogle-search">[Source]</a>
</span>
</details>


