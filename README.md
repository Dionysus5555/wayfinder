# 🧭 Wayfinder

> Navigation and routing for Home Assistant.

Wayfinder is a native Home Assistant integration that brings modern mapping and routing directly into Home Assistant.

Find places, calculate routes and build travel-aware automations using a simple, consistent interface.

---

## Features

- 📍 Intelligent place search
- 🚗 Route planning
- 🗣️ Home Assistant Conversation support
- 🤖 Automation-friendly services
- 🔌 Extensible provider architecture

---

## Installation

1. Copy `custom_components/wayfinder` into your Home Assistant configuration.
2. Restart Home Assistant.
3. Add your Google Maps API key:

```yaml
wayfinder:
  google_maps_api_key: !secret google_maps_api_key
```

4. Restart Home Assistant again.

---

## Services

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

Returns:

- Journey time
- Distance
- Google Maps link
- Structured response data

---

## Voice Example

Ask:

> **"How do I get to Longleat?"**

Wayfinder responds:

> *"The journey to Longleat is about 22 minutes and 13.1 miles."*

---

## Architecture

```text
Home Assistant
        │
        ▼
   Wayfinder
        │
        ▼
Provider Manager
        │
 ┌──────┴──────┐
 ▼             ▼
Google     Future Providers
```

The provider architecture makes it easy to support additional mapping and transport services without changing your automations.

---

## Roadmap

- 🚶 Walking routes
- 🚲 Cycling routes
- 🚆 Public transport
- 📍 Nearby search
- ⭐ Favourite places
- 🔌 Additional providers
- 🧩 HACS support

---

## Contributing

Contributions, ideas and bug reports are always welcome.

---

## License

MIT License
