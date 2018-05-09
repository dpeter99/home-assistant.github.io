---
layout: page
title: "Google Assistant"
description: "Enhance your Hass.io installation with Google Assistant."
date: 2017-04-30 13:28
sidebar: true
comments: false
sharing: true
footer: true
featured: true
---

<p class='note'>
  If you want to integrate your Google Home, or mobile phone running Google Assistant, with Home Assistant, then you want the [Google Assistant component](/components/google_assistant/).
</p>

[Google Assistant][GoogleAssistant] is an AI-powered voice assistant that runs on the Raspberry Pi and x86 platforms and interact via the [DialogFlow][comp] integration with Home-Assistant. You can also use [Google Actions][GoogleActions] to extend its functionality.

To enable access to the Google Assistant API, do the following:

1. In the [Actions On Google Console][project], go to the Projects page. Select an existing project or create a new project
1. Open the project. In the left side of the page go to Device Registration and fill the form out. (you can use any name for the device or the company) 
1. Download and save the ````credentials.json˙``` file

Now install and activate the [Samba] add-on so you can upload your credential file. Connect to the "share" Samba share and copy your credentials over. Name the file `google_assistant.json`.

Next in the Audio crad select the correct deices for the Assistant to use

Now it's time to start Google Assistant for the first time. 

The next step is to authenticate your Google account with Google Assistant. Start the add-on and click on the "OPEN WEB UI" button to start authentication.

### Add-on configuration

Configuration example that uses the USB microphone and the built-in headset audio output on the Raspberry Pi. Note that card and device numbers can differ on your device.

```json
{
  "client_secrets": "google_assistant.json",
  "model_id": "your device ID"
}
```

Configuration variables:

- **model_id**: This is the device ID from the [Actions On Google Console][project] 

### {% linkable_title Home Assistant configuration %}

Use the Home Assistant [DialogFlow component][comp] to integrate the add-on into Home Assistant.

[GoogleAssistant]: https://assistant.google.com/
[GoogleActions]: https://actions.google.com/
[Samba]: /addons/samba/
[comp]: /components/dialogflow/
[project]: https://console.actions.google.com/
[API]: https://console.developers.google.com/apis/api/embeddedassistant.googleapis.com/overview
[oauthclient]: https://console.developers.google.com/apis/credentials/oauthclient
