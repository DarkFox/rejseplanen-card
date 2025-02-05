# PROJECT ARCHIVED
Due to the defunct state of the HA Rejseplanen integration, this project has been archived.

# rejseplanen-card
Lovelace card for listing departures from Rejseplanen sensors

This works with the [Rejseplanen sensor](https://www.home-assistant.io/components/rejseplanen/) included in Home Assistant.

I've tried to add as many styles for different transit types and routes as I could find, but please let me know if any are missing.

![Example](https://raw.githubusercontent.com/DarkFox/rejseplanen-card/master/rejseplanen-card-example.png)

# Installation

## HACS

### Step 1

Search for `Rejseplanen Card` in the "Frontend" tab, then click install.

### Step 2

Link `rejseplanen-card` inside your configuration:

```yaml
resources:
  url: /hacsfiles/rejseplanen-card/rejseplanen-card.js
  type: js
```

## Manual installation

### Step 1

Install `rejseplanen-card` by copying `rejseplanen-card.js` from this repo to `<config directory>/www/rejseplanen-card.js` of your Home Assistant instance.

**Example:**

```bash
wget https://github.com/DarkFox/rejseplanen-card/raw/master/rejseplanen-card.js
mv rejseplanen-card.js ~/.homeassistant/www/
```

### Step 2

Link `rejseplanen-card` inside your configuration.

```yaml
resources:
  url: /local/rejseplanen-card.js?v=0
  type: js
```

## Configuration

Add a custom element in your `ui-lovelace.yaml`

|         Name        |  Type   |    Default   |     Supported options     | Description |
| ------------------- | ------- | ------------ | ------------------------- | ----------- |
| type                | string  | **Required** | `custom:rejseplanen-card` | Type of the card |
| entity              | string  | **Required** | `sensor.rejseplanen`      | entity_id |
| show_scheduled_time | boolean | `false`      | `true`|`false`            | Show the scheduled departure time instead of a countdown in minutes |
| max_entries         | number  | optional     | any number                | Limit number of departures shown |


**Example:**

```yaml
      - type: custom:rejseplanen-card
        entity: sensor.rejseplanen
        show_scheduled_time: true # Optional
        max_entries: 5 # Optional
```


## Credits

Based on [cgtobi](https://github.com/cgtobi) and [DavidMStraub](https://github.com/DavidMStraub)'s work: https://github.com/cgtobi/rmv-card
