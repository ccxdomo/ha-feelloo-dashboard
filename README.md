# Feelloo Dashboard for Home Assistant

[![hacs_badge](https://img.shields.io/badge/HACS-Custom-41BDF5.svg)](https://github.com/hacs/integration)

Beautiful dashboard for [Feelloo](https://feelloo.com) cat trackers in Home Assistant.

## Preview

### Dark Theme
![Preview Dark](screenshots/preview-dark.png)

### Light Theme
![Preview Light](screenshots/preview-light.png)

## Features

- 🗺️ **Interactive Map** — See all your cats on a single map
- 🐱 **Auto-Discovery** — Automatically detects all your Feelloo cats
- 📊 **Status Overview** — Battery, signal strength, home/away status
- ⚡ **Quick Actions** — Toggle Petite Souris, ring the tag
- 🔔 **Smart Alerts** — Charging, low battery, gateway offline
- 🎨 **Theme Adaptive** — Works with both light and dark themes

## Prerequisites

You need the [Feelloo integration](https://github.com/ccxdomo/ha-feelloo) installed and configured.

### Required Cards

Install these custom cards via HACS before using this dashboard:

1. **auto-entities** — `thomasloven/lovelace-auto-entities`
2. **button-card** — `custom-cards/button-card`
3. **card-mod** — `thomasloven/lovelace-card-mod`
4. **stack-in-card** — `RomRider/lovelace-stack-in-card`

## Installation

### Via HACS (Recommended)

1. Open HACS in Home Assistant
2. Go to **Frontend**
3. Click the menu (⋮) and select **Custom repositories**
4. Add `https://github.com/ccxdomo/ha-feelloo-dashboard`
5. Select category **Dashboard**
6. Click **Download**

### Manual

1. Copy `feelloo-dashboard.yaml` to your Home Assistant configuration directory
2. Add it as a new dashboard via the UI or `configuration.yaml`

## Setup

### Method 1: Add to an existing dashboard

1. Go to your dashboard → **Edit Dashboard**
2. Click **⋮** → **Raw configuration editor**
3. Copy the contents of `feelloo-dashboard.yaml`
4. Paste it into the editor
5. Click **Save**

### Method 2: Create a new dashboard

1. Go to **Settings** → **Dashboards**
2. Click **Add Dashboard**
3. Select **Web page** or create a **New dashboard from scratch**
4. In the raw configuration, paste the contents of `feelloo-dashboard.yaml`

## Customization

### Cat Images

To display custom photos for your cats, see the [Feelloo integration documentation](https://github.com/ccxdomo/ha-feelloo#custom-cat-images).

### Entity ID Pattern

This dashboard assumes your Feelloo entities follow the default naming pattern:
- Device tracker: `device_tracker.{cat_name}_name`
- Battery: `sensor.{cat_name}_name_batterie`
- Signal: `sensor.{cat_name}_force_du_signal`
- Home: `binary_sensor.{cat_name}_name_a_la_maison`
- Charging: `binary_sensor.{cat_name}_name_en_charge`
- Low Battery: `binary_sensor.{cat_name}_name_batterie_faible`
- Petite Souris: `switch.{cat_name}_petite_souris`
- Ring: `button.{cat_name}_name_faire_sonner`

If your entities use different names, edit the dashboard YAML to match.

## Support

For issues and feature requests, please use the [GitHub issue tracker](https://github.com/ccxdomo/ha-feelloo-dashboard/issues).

## Credits

- [Feelloo](https://feelloo.com) for the cat trackers
- [Home Assistant](https://home-assistant.io) for the platform
- Custom card authors for their amazing work
