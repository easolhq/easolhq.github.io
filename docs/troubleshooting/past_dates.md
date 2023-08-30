---
layout: default
title: Past dates
parent: Troubleshooting
---

## Past dates are showing as current

An experience has at least one departure date, or [slot start_on]({% link docs/reference/objects/product/experience_slot.md %}#start_on). Currently all departure dates have a start time of 00:00AM UTC on the given date.

Experiences also have a duration, e.g. a music festival might last 3 days. The experience's end date or [slot end_on]({% link docs/reference/objects/product/experience_slot.md %}#end_on) is the date you land on if you do start date + the duration. The end date also has an arbitrary time of 00:00AM UTC.

Easol considers an experience to be 'ongoing' and purchaseable until the end of the day after the end date, to allow for lack of time consideration.

e.g.

| Experience departure date | Experience start_on   | Experience duration | Experience end_on    | Ongoing and purchaseable until |
|:--------------------------|:----------------------|:--------------------|:---------------------|:-------------------------------|
| 24th Aug 2023             | 24th Aug 00:00AM UTC  | 3 hours             | 24th Aug 00:00AM UTC | 25th Aug 23:59PM UTC           |
| 24th Aug 2023             | 24th Aug 00:00AM UTC  | 1 day               | 25th Aug 00:00AM UTC | 26th Aug 23:59PM UTC           |
| 24th Aug 2023             | 24th Aug 00:00AM UTC  | 3 days              | 27th Aug 00:00AM UTC | 28th Aug 23:59PM UTC           |
