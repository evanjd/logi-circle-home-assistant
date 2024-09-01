# Logi Circle component for Home Assistant

This is a custom component to allow you to integrate your [Logi Circle](https://www.logitech.com/en-us/product/circle-2-home-security-camera) cameras into Home Assistant using their public API.

Unfortunately, Logitech stopped accepting applications for access to the Logi Circle API in May 2022. As a result, this component was removed from Home Assistant core as of the 2024.9 release. This repository exists to allow anyone with an existing API key to continue using the component.

> [!WARNING]  
> I no longer use Logi Circle cameras, so I'm unlikely to notice if this component stops working. If you encounter any issues, please feel free to open an issue or a pull request.

## Installation

### HACS

> [!NOTE]  
> Instructions up to date as of HACS 2.0.0.

1. Go to the HACS page in your Home Assistant instance.
2. Click on the three dots in the top right corner and select "Custom repositories".
3. Enter the repository name `evanjd/logi-circle-home-assistant` and select "Integration" from the type dropdown.
4. Click "Add"

### Manual

1. Download the latest release from the [releases page](https://github.com/evanjd/logi-circle-home-assistant/releases)
2. Unzip the downloaded file.
3. Copy the `custom_components/logi_circle` directory to your Home Assistant `config/custom_components` directory.

## Configuration

To integrate cameras linked with your [Logi Circle](https://circle.logi.com/) account, add the following to your `configuration.yaml` file:

```yaml
# Example configuration.yaml entry
logi_circle:
  client_id: YOUR_CLIENT_ID
  client_secret: YOUR_CLIENT_SECRET
  api_key: YOUR_API_KEY
  redirect_uri: YOUR_REDIRECT_URI
```

| Field         | Description                                                                                                                                                      | Required | Type   |
| ------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | ------ |
| client_id     | The client ID issued to you by Logitech.                                                                                                                         | true     | string |
| client_secret | The client secret issued to you by Logitech.                                                                                                                     | true     | string |
| api_key       | The API key issued to you by Logitech.                                                                                                                           | true     | string |
| redirect_uri  | The redirect URI that corresponds to your Home Assistant instance. It must match one of the redirect URIs specified when you requested API access from Logitech. | true     | string |
