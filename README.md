# Real-Time Object Detection with Frigate and Home Assistant

*From the [Thomas Computes YouTube Channel](https://www.youtube.com/c/ThomasComputes)*

*Check out [the video](https://youtu.be/WbvKIVCJF28) about this repository*

---
## Introduction

Thanks for watching my video! If you haven't yet, be sure to check it out! In this repository, I've provided my Frigate Add-on configuration file for home assistant. I'm using a Reolink RLC-520 security camera and a Google Coral USB Tensor accelerator. Here are the links to those products:

- [Reolink RLC-520](https://reolink.com/us/product/rlc-520/)
- [Google Coral USB Accelerator](https://coral.ai/products/accelerator)

You can also find exhaustive documentation about setting up Frigate as a standalone container, service, or add-on to Home Assistant on the [documentation website](https://docs.frigate.video/). I'm going off of the instructions for [using Frigate as an add-on](https://github.com/blakeblackshear/frigate-hass-integration). This project is fully accredited to Blake Blackshear, who you can find [right here on GitHub](https://github.com/blakeblackshear). Thanks Blake!

## Overview

The `frigate.yml` has inline comments to help you make sense of what each step is doing. This file is not ubiquitous and will likely not work with most camera and hardware setups. It's customized for my installation.

There are several parameters that are required to get frigate to work as you want. The most important are setting up the correct parameters for your camera and your detector(s). You'll need to understand how your camera streams video. In my case, it's in FLV over HTTP, as you can see from my input path:

```
http://{YOUR-IP-ADDRESS}/flv?port=1935&app=bcs&stream=channel0_main.bcs&user={user}&password={password}
```

You'll also need to provide the username and password you use to sign into your camera as a user. You can configure this in the Reolink app, or via the camera's web server, accessible via its IP address. Security here is important, and it's always a good idea to keep passwords and other sensitive information out of plain-text files. More information about how to securely store secrets in Home Assistant can be found [here](https://www.home-assistant.io/docs/configuration/secrets/).

## Future Work

I will keep tabs on this repository as time goes on and look out for any questions people have about the setup. Feel free to file a new issue in this repo, and I will get back to you as soon as I can! I'll update this readme with more helpful tips as I get more feedback.

## Thanks To The Following:

- [Blake Blackshear (Creator of Frigate)](https://github.com/blakeblackshear)
- [Jason Hunter (hunterjm on GitHub) - Author of the Frigate Notification Blueprint for Home Assistant](https://gist.github.com/hunterjm/8ff0005104dce3f28923294f49a443b1)
