# Prefer Timespan

Instead of `int XXXInterval = 10;` (or a slightly better version: `int XXXIntervalInMinute = 10`) and later convert it to milliseconds like this `XXXIntervalIn * 60 * 1000`, you can use `XXXInterval = Timespan.FromMinutes(10)` and later convert it to milliseconds by `XXXInterval.TotalMilliseconds`.