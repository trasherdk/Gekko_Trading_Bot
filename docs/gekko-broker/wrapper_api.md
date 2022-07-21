# Wrapper API

Gekko Broker is a library that sits between trading applications and Gekko Broker Exchange Wrappers. Which means it has two APIs to communicate with other code:

![diagram describing Gekko Broker API interface](https://user-images.githubusercontent.com/969743/41892153-566293a0-7941-11e8-9998-7a5b5b554ffd.png)

This document descibres the API layer between the exchange wrappers and Gekko Broker.

## Wrapper API spec

The current API documentation is currently located [here](../extending/add_an_exchange.md).

## Wrapper API Changelog

### Gekko 0.5.x to Gekko (Broker) 0.6.0

NOTE: this API design might still have minor changes leading up to the release of Gekko 0.6. See [this thread](https://forum.gekko.wizb.it/thread-57279-post-59207.html) for more information.

- The wrapper files are now nested different (from `gekko/exchanges` to `gekkobroker/wrappers` (which equals `gekko/exchange/wrappers` for Gekko users).
- cancelOrder now requires a second parameter to be passed (that indicates whether the order was filled before it was canceled), see details.
- checkOrder now expects an object with a few properties to be returned, see details.
- Error handling has gotten a lot more complex, with an updated error interface between a retry system (provided by Gekko) and the exchange wrapper.
