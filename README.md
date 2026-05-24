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

### Required Integration

You need the [Feelloo integration](https://github.com/ccxdomo/ha-feelloo) installed and configured.

### Required Custom Cards (MANDATORY)

**⚠️ The dashboard will NOT work without these cards installed.**

Install via **HACS** → **Frontend** → **⋮** → **Custom repositories**:

| Card | Repository | Purpose |
|------|-----------|---------|
| **auto-entities** | `thomasloven/lovelace-auto-entities` | Auto-discovery of all Feelloo entities |
| **card-mod** | `thomasloven/lovelace-card-mod` | Styling (rounded corners, borders) |

**After installing each card, restart Home Assistant.**

### Verify Installation

1. Go to **Developer Tools** → **States**
2. Check that your Feelloo entities exist (e.g., `device_tracker.pinceau_name`)
3. If entities are missing, the Feelloo integration is not configured correctly

## Installation

### Step 1: Install Dependencies

1. **HACS** → **Frontend** → **⋮** → **Custom repositories**
2. Add `https://github.com/thomasloven/lovelace-auto-entities` (Category: **Lovelace**)
3. Add `https://github.com/thomasloven/lovelace-card-mod` (Category: **Lovelace**)
4. **Restart Home Assistant**

### Step 2: Add the Dashboard

**Via HACS:**
1. **HACS** → **Frontend** → **⋮** → **Custom repositories**
2. Add `https://github.com/ccxdomo/ha-feelloo-dashboard`
3. Select category **Dashboard**
4. Click **Download**

**Manual:**
1. Copy the contents of `feelloo-dashboard.yaml`
2. Go to your dashboard → **Edit Dashboard**
3. Click **⋮** → **Raw configuration editor**
4. Paste the YAML
5. Click **Save**

### Step 3: Configure the Map

The dashboard uses a placeholder `{cat_name}` for the map card. You need to replace it with your cat's entity ID.

1. Go to **Developer Tools** → **States**
2. Find your cat's device tracker entity (e.g., `device_tracker.pinceau_name`)
3. Note the slug part (e.g., `pinceau`)
4. Edit the dashboard YAML and replace `{cat_name}` with your cat's slug

**Example:**
```yaml
entities:
  - entity: device_tracker.pinceau_name
```

For multiple cats, add more lines:
```yaml
entities:
  - entity: device_tracker.pinceau_name
  - entity: device_tracker.tibounet_name
```

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
