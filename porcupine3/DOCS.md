# Home Assistant Add-on: Porcupine Wake Word (v3)

## Installation

Follow these steps to get the add-on installed on your system:

1. Click the Home Assistant My button below to add the add-on repository to your Home Assistant instance.

   [![Open your Home Assistant instance and show the add add-on repository dialog with a specific repository URL pre-filled.](https://my.home-assistant.io/badges/supervisor_add_addon_repository.svg)](https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https%3A%2F%2Fgithub.com%2Fvash2695%2Fmitts-hass-addons)

2. Find the "Porcupine Wake Word (v3)" add-on and click install.

## Access Key

This version of Porcupine requires an access key from Picovoice to function. To get an access key:

1. Create a free account at [Picovoice Console](https://console.picovoice.ai/)
2. Create a new access key in the console
3. Copy the key and paste it into the "access_key" field in the add-on configuration

## Configuration

Example configuration:

```yaml
access_key: YOUR_ACCESS_KEY_HERE
sensitivity: 0.5
language: en
debug_logging: false
```

### Option: `access_key` (required)

The access key from Picovoice Console. See above for instructions on obtaining the key.

### Option: `sensitivity` (optional)

The sensitivity of wake word detection (0-1). A higher value increases sensitivity, potentially leading to more false activations. A lower value makes detection more strict but may require louder/clearer speech.

Default value: `0.5`

### Option: `language` (optional)

The language for wake word detection. Currently supported languages:

- `en` - English
- `es` - Spanish
- `fr` - French
- `de` - German

Default value: `en`

### Option: `debug_logging` (optional)

Controls whether additional debug information should be logged.

Default value: `false`

## Integration with Home Assistant

This add-on creates a Wyoming service that's automatically discovered by Home Assistant. To use it in your voice assistant pipeline:

1. Go to Settings → Voice Assistants
2. Create a new pipeline or edit an existing one
3. Under "Wake Word", select "Porcupine Wake Word (v3)" 
4. Choose your preferred wake word from the dropdown

## Support

For support, please use the [Home Assistant forums](https://community.home-assistant.io/) or [GitHub issues](https://github.com/vash2695/wyoming-porcupine/issues). 