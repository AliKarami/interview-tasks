# Surge

In a ride-hailing application, some-times environmental conditions breaks the supply/demand balance based on our base price formulas, so we had to follow the demand somehow.

In order to solve this, we need to know the rate of demand on each district separately, and if goes higher than a threshold, apply a factor to the price of those areas.

let's assume we reduce our problem to just a city, Tehran.
these are the project requirements:
1. We work with municipality districts, these polygons are available in the OpenStreetMap data.
2. Your Application should provide a REST API to get called on each ride, you will only get latitude and longitude of the origin of the ride.
3. In each district, rate of the ride requests has direct correlation with the demand in that district, regardless of the district area.
4. Demand is a time-dependent concept, requests in the morning shouldn't take effect on the demand metric in the evening, so there should be dynamic time-window.
5. We need to get informed of any changes in the demand state to apply it on our price in realtime.
