# hacs-onkyo-repository

This repo contains an Onkyo/Pioneer Custom component based off a PR that is taking a long time to make it to master.
(it started in April 2021). 

This version uses an async Onky client so responses are faster. 

I am not the author of this just providing it so others have access.

History

A [PR](https://github.com/home-assistant/core/pull/48640) was raised on 2nd April 2021 to update the Onkyo component to a new Async one. 
I tested this from the PR and I have been using it ever since. It is significantly quicker than the version in the main repo.

The PR was closed on the 4th April 2021 as it wasn't configurable via the UI.

On 10th Nov 2021 another [PR](https://github.com/home-assistant/core/pull/59518) was created including the UI element however 
as it stands the Home Assistant team say this PR is too big and so it is stuck in limbo.

This repo is based off the original PR and as such doesn't include the UI configurable element. 

To configure you need to use yaml just like the Home Assistant component.

The major change from the official integration is that `max_volume` and `receiver_max_volume` have been combined into
a single setting. You can find the official components documentation here: https://www.home-assistant.io/integrations/onkyo/

```
  - platform: onkyo
    host: 192.168.1.40
    name: Studio Amplifier
    sources:
      strm-box: "Satalite box"
      video2: "Matrix"
      # dvd: "DVD"
      game: "Computer"
      cd: "Snapcast"
      aux1: "AUX"
      phono: "PHONO"
      tv: "TV"
      net: "Net"
      fm: "FM Radio"
      am: "AM Radio"
      usb: "USB Front"
      bluetooth: "Bluetooth"
    max_volume: 150
    zones:
      zone2:
        # Both defined
        name: Back Garden Zone
        max_volume: 150
      # Not connected at the moment
      #zone3:
      #  name: Courtyard Zone
      #  max_volume: 150
```
