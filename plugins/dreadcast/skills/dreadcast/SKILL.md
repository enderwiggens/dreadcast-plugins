---
name: dreadcast
description: Use when the person asks about the weather, radar, storms, weather alerts, wildfires, tropical storms or what Dreadcast is showing, or asks you to show something on the Dreadcast map or change its layers, radar range, saved views, notifications or location.
---

# Using Dreadcast

Dreadcast is a weather and radar app running on this Mac. Its MCP tools read what the app shows and change what it
shows. The app is the source of truth; never estimate weather yourself.

## Reading

- Start with `get_status`. It reports the place, conditions, radar settings, which layers are on, event counts and
  data problems.
- `list_events` returns alerts, wildfires and tropical storms with IDs. A `null` list means the source isn't
  monitored, not that there is nothing. Offer to turn on the matching layer with `set_layers`.
- `get_alert` returns official National Weather Service text. Quote the headline and instruction verbatim, give the
  expiry, and name the NWS. Never shorten an instruction or say the person is safe.
- `get_forecast` values are forecasts, not observations. Say when they were fetched.
- Every event has a `link` (`dreadcast://…`) that opens it in the app. Include it when it helps.

## Changing what Dreadcast shows

- `show_on_map`, `open_reader`, `set_layers`, `set_radar`, `apply_view` and `save_view` act immediately. Dreadcast
  shows each change with an Undo button, so describe what you changed in one sentence.
- `set_location` and `set_notifications` ask the person to confirm in Dreadcast. Tell them to look for the prompt and
  wait for the result. A declined or timed-out request changed nothing.
- If a tool says assistant access is off, the person can allow it in Dreadcast → Settings → Assistants.

## Don't

- Don't invent arrival times, probabilities or readings the tools didn't return.
- Don't turn missing or stale data into reassurance. Say what is unavailable and since when.
- Don't joke about active warnings.
