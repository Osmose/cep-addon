# CEP Add-on Enrollment
[CEP][] plugin that estimates the number of users who have the an add-on
installed per-day.

[CEP]: https://docs.telemetry.mozilla.org/concepts/data_pipeline.html#hindsight

## Sample Configuration
```lua
filename = 'timecop_addon_estimates.lua'
message_matcher = 'Type=="telemetry" && Fields[docType]=="main"'
preserve_data = true
ticker_interval = 60
addon_id = 'timecop@mozilla.com'
```

## Sample Output
Keys are the date in `YEARMONTHDAY` format, values are the estimated number of
users who sent a ping that included the add-on ID that day.
```json
{
  "20171001": 4523,
  "20171002": 5937,
  "20171003": 3002
}
```

## License
CEP Add-on Enrollment is licensed under the MPLv2. See the `LICENSE` file for
details.
