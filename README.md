# rejseplanen-card
Lovelace card for listing departures from Rejseplanen sensors

This currently only works with my [Custom Rejseplanen](https://github.com/DarkFox/custom_rejseplanen) component. When I'm happy with it, I plan to make a pull request on the built-in Rejseplanen component in HA

I've tried to add as many styles for different transit types and routes as I could find, but please let me know if any are missing.

## Installation

### Step 1

Install `rejseplanen-card` by copying `rejseplanen-card.js` from this repo to `<config directory>/www/rejseplanen-card.js` of your Home Assistant instance.

**Example:**

```bash
wget https://github.com/DarkFox/rejseplanen-card/raw/master/rejseplanen-card.js
mv list-card.js ~/.homeassistant/www/
```

### Step 2

Set up the Rejseplanen transport sensor.

**Example:**

```yaml
sensor:
  - platform: custom_rejseplanen
    name: S-Tog Nørreport til Høje Tåstrup
    stop_id: '008600646'
    route: B
    departure_type: S
    direction:
      - Høje Taastrup St.
```

### Step 3

Link `rejseplanen-card` inside you `ui-lovelace.yaml`.

```yaml
resources:
  - url: /local/rejseplanen-card.js?v=0
    type: js
```

### Step 4

Add a custom element in your `ui-lovelace.yaml`

**Example:**

```yaml
      - type: "custom:rejseplanen-card"
        entity: sensor.s_tog_norreport_til_brondbyoster
```


## Credits

Based on [cgtobi](https://github.com/cgtobi) and [DavidMStraub](https://github.com/DavidMStraub)'s work: https://github.com/cgtobi/rmv-card
