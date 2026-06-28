# 🧭 Wayfinder

> A modern navigation framework for Home Assistant.

Wayfinder is a native Home Assistant integration that provides a single, consistent interface for navigation, routing and location services.

Today it supports Google Maps for intelligent place search and route planning. Tomorrow it can support public transport, multiple map providers, nearby search, EV routing and more—all without changing your automations.

---

## Features

* 📍 Natural language place search
* 🚗 Driving route calculation
* 🗣️ Home Assistant Conversation support
* 🤖 Automation-friendly services
* 🔌 Provider-based architecture
* 🧩 Designed for future expansion

---

## Why Wayfinder?

Home Assistant has excellent mapping and device tracking, but there isn't a unified integration dedicated to navigation.

Wayfinder aims to solve that by providing a single API for:

* Finding places
* Calculating routes
* Planning journeys
* Public transport
* Nearby search
* Future navigation providers

Your automations remain the same, regardless of which provider powers them.

---

## Installation

Copy the integration into:

```text
config/custom_components/wayfinder/
```

Add your API key:

```yaml
wayfinder:
  google_maps_api_key: !secret google_maps_api_key
```

Restart Home Assistant.

---

## Example

### Find a place

```yaml
action: wayfinder.find_place
data:
  query: Longleat
```

### Calculate a route

```yaml
action: wayfinder.route
data:
  destination: Longleat
  travel_mode: DRIVE
```

Voice example:

> "How do I get to Longleat?"

↓

> "The journey to Longleat is about 22 minutes and 13.1 miles."

---

## Architecture

```
Home Assistant
        │
        ▼
   Wayfinder
        │
        ▼
 Provider Manager
        │
 ┌──────┴─────────────┐
 ▼                    ▼
Google         Future Providers
```

The provider architecture allows new mapping and transport services to be added without changing your Home Assistant automations.

---

## Roadmap

### v0.2

* Walking routes
* Cycling routes

### v0.3

* Nearby search
* Favourite places
* Reverse geocoding

### v0.4

* Public transport
* Live train routing
* Station search

### v1.0

* Multiple providers
* HACS release
* Complete navigation framework

---

## Contributing

Ideas, bug reports and pull requests are always welcome.

---

## License

MIT License
