---
title: "Online Privacy Guide"
date: 2022-12-08T09:41:23+02:00
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

You cannot have both **privacy** and **convenience**. There is always a tradeoff
between the two. For this reason it is important to establish a personal threat
model you want to protect against, to know how far to go. The goal should be
obtaining a balance between the two, not going all out on one.

{{< image src="/images/pepe-paranoid.webp" position="center" style="width: 50%" >}}

### Possible thread models

1. Strangers
2. Family, friends
3. Stalkers
4. Companies
5. Governments
6. **Everyone**

The lower on the list, the higher privacy you should seek. This guide will help
you improve only your online privacy. If you set a thread model between the
last two, you should also look into hardware privacy, such as [libre boot](https://libreboot.org/)
and [degoogled Android phone](https://grapheneos.org/).

# Step 1 - Browser

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
<a style='margin-right: 10px' href="">[Download]</a>
<a href="">[Website]</a>
</span>
</details>

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
<a style='margin-right: 10px' href="">[Download]</a>
<a href="">[Website]</a>
</span>
</details>

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

<span class="i-blog">
<a style='margin-right: 10px' href="">[Download]</a>
<a href="">[Website]</a>
</span>
</details>

## [Ungoogled Chromium](https://github.com/ungoogled-software/ungoogled-chromium)

[{{< image src="/logos/chromium.svg" position="center" style="width: 25%;" >}}](https://github.com/ungoogled-software/ungoogled-chromium)

{{< text-icon privacy "#00FF11" >}} Privacy level: **{{< color "High" "#00FF11" >}}**

**Ungoogled Chromium** is Google Chrome without **trackers**, **ads**,
**phoning home**, **Google search engine**, **Google Extension Store**,
**Google accounts**. Therefore, it is very minimal and does not provide any
privacy features out of the box.

Its downside is that you have to compile it and it is not user-friendly,
installing extensions being a tedious task. However, if you need a chromium
based browser, it is the best solution out there.

## [Brave](https://brave.com/)

[{{< image src="/logos/brave.svg" position="center" style="width: 25%;" >}}](https://brave.com/)

{{< text-icon privacy "#FFAA00" >}} Privacy level: **{{< color "Medium" "#FFAA00" >}}**

**Brave** is the browser based on Chromium that advertised itself as **the**
browser for privacy. It comes with good privacy features outside the box,
however it is known for adding spyware features in the past, such as
**telemetry**, **auto-updates** and **Brave Rewards**.

Should be used if Chromium engine is required and Ungoogled Chromium cannot be
compiled in a reasonable amount of time.

### Now that you chose a browser, we should focus on your web activity.

# Step 2 - Privacy friendly services

Even if you have a secure browser, your data is still accesible if you **simply
hand it over** to Google, Facebook or other companies. You should aim to
replace **all of your services** from these companies with privacy-friendly
alternatives.

You can see the privacy-friendly services **hosted by ElPengu** [here](../../services).

## Search Engines

### {{< image src="/logos/librex.png" position="relative" style="height: 2.15rem; width: 2.15rem; margin-right: 15px" >}} [LibreX](https://github.com/hnhx/librex/)

{{< image src="/images/librex-interface.webp" position="center" style="width: 75%" >}}

{{< text-icon privacy "#55FF55" >}} Privacy level: **{{< color "Very high" "#55FF55" >}}**

**LibreX** is a meta search engine that pulls Google results. It uses **no
javascript**, therefore your search queries can't be tracked.

Other useful features are torrent search and onion link search.

### {{< image src="/logos/searx.png" position="relative" style="height: 2.15rem; width: 2.15rem; margin-right: 15px" >}} [SearXNG](https://github.com/searxng/searxng)

{{< image src="/images/searxng-interface.webp" position="center" style="width: 75%" >}}

{{< text-icon privacy "#00FF11" >}} Privacy level: **{{< color "High" "#00FF11" >}}**

**SearXNG** is a fork of SearX, a meta search engine that pulls results from
**a lot** of search engines, including Google, DuckDuckGo, StartPage. It
requires javascript for proper use, which can be maliciously modified by the
host, but has the advantage of being customizable.
