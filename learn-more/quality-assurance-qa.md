# Software Quality Assurance (SQA)

Our main goal is to provide you with fast and reliable open-source services. To achieve this, we collect performance data about the navigation and the application feature usage, and send anonymous usage statistics to our servers. This data helps us track how changes affect the performance and stability of our open-source service and identify potential issues.

We are fully transparent about what data we collect, why we collect it, and how it's transmitted. The source code for the telemetry package is open-source and can be found [**here**](https://github.com/PostHog/posthog). If you do not want to share telemetry data and help improve our projects, you can opt out of this feature.

### Data Processing

To provide a clear understanding of why we collect data, how it's collected, and what we do with it, as well as real-world examples of how this data has improved our projects, let's break down the data processing pipeline:

1. Telemetry data is collected from the browser.
2. This data is periodically sent to `eu.posthog.com`.
3. The data is stored and analyzed using the PostHog platform.

Our data processing pipeline has been designed with specific goals in mind:

* To track the number of dyrector.io installs.
* To understand which features are in use and how they are utilized.
* To evaluate the frequency of specific feature usage.
* To detect issues introduced by new features, such as buggy releases.

### Opting Out

1. You have the option to disable quality assurance features, also known as telemetry, by using the environment variable `QA_OPT_OUT=true`. Disabling telemetry doesn't have any drawbacks, except that it prevents us from making improvements to the project.

### Data Privacy

In order to safeguard your privacy, we take several measures to protect your data:

1. We are unable to access or store the IP address of your host or users. Our PostHog project's "Discard client IP data" is active, thus we are not able to identify who sent the data. You can find a comprehensive list of transmitted URL paths in the Request Telemetry section.
2. We do not transmit any environment information from the host except for:
   * Operating system (e.g., Windows, Linux, OSX)
   * Target architecture (e.g., amd64, darwin, ...)
   * Display dimensions
   * Browser data (e.g., Firefox, Chrome, English, browser version)

All this information is stored in an aggregated format without any personally identifiable data, ensuring your privacy is protected.

### Identification

To facilitate the identification of installations each running instance is assigned a unique identifier generated using a Universally Unique Identifier (V4). This identification process is triggered when we are confident that the instance is not a test instance, such as a tutorial or a local installation.

The system metrics we collect include:

* `$os`: The operating system of the user's device.
* `$browser`: The web browser used by the user.
* `$device_type`: The type of device used, such as "Desktop" or "Mobile."
* `$browser_version`: The version of the web browser.
* `$browser_language`: The language of the web browser.
* `$screen_height`: The height of the user's screen in pixels.
* `$screen_width`: The width of the user's screen in pixels.
* `$viewport_height`: The height of the viewport in pixels.
* `$viewport_width`: The width of the viewport in pixels.
* `$lib`: This'll always be web.
* `$lib_version`: The type of PostHog library.
* `$insert_id`: An identifier associated with the insertion.
* `$time`: A timestamp associated with the event.
* `distinct_id`: A distinct identifier for the user or event.
* `$device_id`: The identifier associated with the user's device.
* `$groups`: A dictionary of group identifiers.

These measures allow us to effectively manage and group installations while maintaining data security and privacy.

### Source code

The full code-base is open source.

* [**dyrector.io**](https://github.com/dyrector-io/dyrectorio)
* [**PostHog**](https://github.com/PostHog/posthog)

### Example

```json
{
  "uuid": "018b8632-5d72-7461-95e1-985aaa8590e7",
  "event": "select-chip",
  "properties": {
    "$os": "Linux",
    "$browser": "Firefox",
    "$device_type": "Desktop",
    "$pathname": "/[teamSlug]/nodes",
    "$browser_version": 119,
    "$browser_language": "en-US",
    "$screen_height": 1080,
    "$screen_width": 1920,
    "$viewport_height": 921,
    "$viewport_width": 1093,
    "$lib": "web",
    "$lib_version": "1.85.2",
    "$insert_id": "38hidmng7xk5jtet",
    "$time": 1698763529.587,
    "distinct_id": "018b860e-5987-79b1-ac1e-eaf008c67fcd",
    "$device_id": "018b860e-5987-79b1-ac1e-eaf008c67fcd",
    "$groups": {
      "dyoInstance": "8c5c8b11-3c21-4d5a-b09b-fefb56647aaf"
    },
    "$console_log_recording_enabled_server_side": false,
    "$session_recording_recorder_version_server_side": "v2",
    "$autocapture_disabled_server_side": true,
    "$active_feature_flags": [],
    "$feature_flag_payloads": {},
    "$referrer": "$direct",
    "$referring_domain": "$direct",
    "elementType": "button",
    "label": "nodeType-docker",
    "token": "phc_wc4nEUy7HYW8Elf8G9jiccvl2ZYt8pVts8NVBRMPzHu",
    "$session_id": "018b860e-5988-748e-9880-ab38ffb8c284",
    "$window_id": "018b860e-5988-748e-9880-ab39b3e577af",
    "$set": {
      "$os": "Linux",
      "$browser": "Firefox",
      "$device_type": "Desktop",
      "$pathname": "/[teamSlug]/nodes",
      "$browser_version": 119,
      "$referrer": "$direct",
      "$referring_domain": "$direct"
    },
    "$set_once": {
      "$initial_os": "Linux",
      "$initial_browser": "Firefox",
      "$initial_device_type": "Desktop",
      "$initial_pathname": "/[teamSlug]/nodes",
      "$initial_browser_version": 119,
      "$initial_referrer": "$direct",
      "$initial_referring_domain": "$direct"
    },
    "$sent_at": "2023-10-31T14:45:29.624000+00:00",
    "$group_0": "8c5c8b11-3c21-4d5a-b09b-fefb56647aaf"
  },
  "timestamp": "2023-10-31T14:45:35.050Z",
  "team_id": 10816,
  "distinct_id": "018b860e-5987-79b1-ac1e-eaf008c67fcd",
  "elements_chain": "",
  "created_at": "2023-10-31T14:45:35.132Z"
}
```
