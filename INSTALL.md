# Installation

* Install and configure [HACS](https://hacs.xyz/)

* Within HACS install the following
  * [button-card](https://github.com/custom-cards/button-card) (Frontend)
  * [layout-card](https://github.com/thomasloven/lovelace-layout-card) (Frontend)
  * [Swipe Card](https://github.com/bramkragten/swipe-card) (Frontend)

* Manually copy over these files from [anarion80/hass-config](https://github.com/anarion80/hass-config)
  * `ui-lovelace-tablet.yaml`
  * `button_card_templates` folder
  * `popup` folder
  * `themes` folder
  * `sidebar.yaml`

* In `configuration.yaml` add lines [[docs](https://www.home-assistant.io/lovelace/dashboards/)]

  ```yaml
  frontend:
    themes: !include_dir_merge_named themes
  template: !include sidebar.yaml

  lovelace:
    mode: yaml #use ui-lovelace-tablet.yaml
    resources: #hacs
      - url: /hacsfiles/button-card/button-card.js
        type: module
      - url: /hacsfiles/lovelace-layout-card/layout-card.js
        type: module
      - url: /hacsfiles/swipe-card/swipe-card.js
        type: module
  ```

* In `secrets.yaml` add placeholders

  ```yaml
  youtube_token: abc
  apexcharts_tibber: abc
  apexcharts_influx: abc
  apexcharts_github: abc
  ```

* [Restart](https://my.home-assistant.io/redirect/server_controls/) Home Assistant

* **Select [tablet theme](https://my.home-assistant.io/redirect/profile/) ← DON'T SKIP THIS STEP!**

Then add your entities, [browser_mod](https://github.com/thomasloven/hass-browser_mod) for popups etc...
