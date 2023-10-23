# Pairdrop

This addon packages the [Pairdrop](https://github.com/schlagmichdoch/PairDrop) project for deployment on your
local Home Assistant instance.

# Description

<div align="center">
  <a href="https://github.com/schlagmichdoch/PairDrop">
    <img src="https://raw.githubusercontent.com/schlagmichdoch/PairDrop/master/public/images/android-chrome-512x512.png" alt="Logo"  width="150" height="150">
  </a>
 
  <h1>PairDrop</h1>

  <p>
    Local file sharing in your browser. Inspired by Apple's AirDrop.
    <br />
    <a href="https://pairdrop.net"><strong>Explore  »</strong></a>
  </p>
</div>

## Features
[PairDrop](https://pairdrop.net) is a sublime alternative to AirDrop that works on all platforms.

- File Sharing on your local network
  - Send images, documents or text via peer to peer connection to devices on the same local network.
- Internet Transfers
  - Join temporary public rooms to transfer files easily over the internet!
- Web-Application 
  - As it is web based, it runs on all devices.

You want to quickly send a file from your phone to your laptop?
<br>You want to share photos in original quality with friends that use a mixture of Android and iOS?
<br>You want to share private files peer to peer between Linux systems?
<br>AirDrop is unreliable again?
<br>_Send it with PairDrop!_

## Authors & contributors

The original author of Pairdrop maintains the upstream source repository [here](https://github.com/schlagmichdoch/PairDrop).

## Installation

This addon requires the `nginx-proxy-manager` addon or similar to provide web hosting for it's default interface.

1. Click the Home Assistant My button below to open the add-on on your Home
   Assistant instance.

   [![Open this add-on in your Home Assistant instance.][addon-badge]][addon]

1. Click the "Install" button to install the add-on.
1. Start the "Pairdrop" add-on
1. Check the logs of the "Pairdrop" add-on to see if everything went well.

## Reverse Proxy Configuration

To add a reverse proxy to Pairdrop, you will reverse proxy to the internal hostname of the container.

Using `nginx-proxy-manager` and this repository, you would reverse proxy to `wrouesnel-pairdrop:3000`.
Make sure to enable Websocket Support.

## TURN Server Configuration

In complicated network environments you may need to install or specify a TURN server in order to get reliable
communications between peers using WebRTC. The `rtc_config` object should be updated with TURN server details
if you do this.

[addon-badge]: https://my.home-assistant.io/badges/supervisor_addon.svg
[addon]: https://my.home-assistant.io/redirect/supervisor_addon/?addon=pairdrop&repository_url=https%3A%2F%2Fgithub.com%2Fwrouesnel%2Faddon-pairdrop