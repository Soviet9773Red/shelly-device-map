## Simple Shelly Home Map

A lightweight, static HTML template for visualizing Shelly devices on a house or apartment floor plan.
Intended to be used together with custom Shelly scripts (for example [shelly-elprisSE](https://github.com/Soviet9773Red/shelly-elprisSE) ) running directly on the devices.

It helps visualize device placement, IP addresses, and provides quick access to the Shelly Web UI, running scripts, and status pages for monitoring parameters such as memory usage, temperature, and Wi-Fi signal.

The template is fully static and requires no backend or server-side logic.
It can be opened locally or hosted on a Raspberry Pi using a minimal web server.
The project is intentionally kept minimal:

- no backend, no databases
- no Home Assistant, no MQTT and no mandatory JavaScript.

Everything works as static HTML and CSS.
The page can be opened directly from a local PC or served from a Raspberry Pi using a minimal built-in web server (for ex., a simple Python HTTP server).
This approach allows users to build a clear and practical home overview without introducing additional infrastructure or complexity.

 [Live demo](https://soviet9773red.github.io/shelly-device-map/)

> Note: Device links in the live demo use example local IP addresses  
> and will not work in your network unless they match your own device IPs.


### Features

- Fully static HTML + CSS
- Manual device positioning using CSS variables
- Works locally, on Raspberry Pi, or GitHub Pages
- No Home Assistant, MQTT, or server required
- Easy to extend with optional JavaScript modules



### How it works

Each device is positioned manually using inline CSS variables:

```html
<div class="device" style="--top:25; --left:50;">
```

--top - vertical position in percent
--left - horizontal position in percent

Devices are positioned relative to the floor map image.

Folder structure:

```
/
├── index.html
├── maps/
│   ├── floor00.jpg
│   └── floor01.jpg
├── img/
│   ├── favicon.ico
│   ├── plus1pm.jpg
│   ├── plus1.jpg
│   ├── pro3.jpg
│   ├── plusHT.jpg
│   └── plugS.jpg
└── README.md

```

### Installation and file structure

To use this template, keep the directory structure unchanged.
Copy the following structure to your local computer or server:

```
/
├── index.html
├── maps/
│   └── your-floor-images.jpg
├── img/
│   └── device-icons.jpg
```

* **index.html**
Main entry point of the project.
This file contains the full layout and configuration.

* **maps/**
Contains floor plan images.
Replace the default images with your own floor maps.

* **img/**
Contains device icons.
You may add your own images if a device type is missing.

The file index.html can be opened directly in a browser
or served from any simple web server.


### File naming

The main file is named index.html by default.
This is intentional and allows:

* easy local usage,

* automatic support by GitHub Pages,

* compatibility with minimal HTTP servers.

If needed, you may rename index.html to another name
(for example shelly-device-map.html),
but in most cases this is not recommended.


### External links and notes

You can place additional notes or external links directly on the map:

```html
<div class="external-links" style="top:5%; left:5%;">
    <span class="note">Electricity prices</span>
    <a href="https://www.elprisetjustnu.se/">elprisetjustnu.se</a>
</div>
```

### IP addresses

All IP addresses in this repository use private RFC1918 ranges (for example, 192.168.x.x) and are intended for local testing only.
Before using the template in your own environment, all IP addresses must be replaced manually to match the actual addresses of your Shelly devices.   
For detailed configuration instructions, device block examples, and customization guidelines, please refer to the additional documentation:
[device-config.md](https://github.com/Soviet9773Red/shelly-device-map/blob/main/device-config.md)


### Intended usage

This project is designed for people who want a **simple and transparent overview**
of their Shelly setup without introducing complex infrastructure.

It is suitable for:
- local use on a PC,
- hosting on a Raspberry Pi,
- testing and prototyping a Shelly-based home setup.

Basic HTML knowledge is required for customization, but no advanced programming skills are needed.

---

License: MIT License: © 2026 Alexander [S9773R](https://github.com/Soviet9773Red)
