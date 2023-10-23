# Home Assistant Add-on: Pairdrop

## About

This add-on enables you to easily share files between different devices in your home,
similar to Apple Airdrop but with no local app requirements and supporting all platfroms.

This addon should be used with nginx-proxy-manager to provide TLS support for the frontend.

## Installation

   [![Open this add-on in your Home Assistant instance.][addon-badge]][addon]

Make sure to checkout the [documentation](pairdrop/DOCS.md) for more details on installation. You will need
[nginx-proxy-manager](https://github.com/hassio-addons/addon-nginx-proxy-manager) (or [my fork with client certificate support](https://github.com/wrouesnel/addon-nginx-proxy-manager)) or similar to expose the web
interface securely. You may also need [coturn](https://github.com/wrouesnel/addon-coturn) in order to get RTC
working inside your network if you have a more complicated configuration.

[addon-badge]: https://my.home-assistant.io/badges/supervisor_addon.svg
[addon]: https://my.home-assistant.io/redirect/supervisor_addon/?addon=pairdrop&repository_url=https%3A%2F%2Fgithub.com%2Fwrouesnel%2Faddon-pairdrop