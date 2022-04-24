
# Surge  
  
In a ride-hailing application, sometimes environmental conditions break the supply/demand balance, and our base price formulas wouldn't satisfy the market requirements, so we had to follow the demand fluctuations somehow.  
  
In order to solve this, we decided to apply a factor on the price of the city districts, which has a demand rate more than a threshold. For example, if a district has more than 10K requests in the last hour, we multiply the prices of the district by 1.15.  
  
To provide a PoC to the product team, we reduce the problem to just a city, Tehran.  
  
These are the project specifications:  
1. We work with municipality districts; these polygons are available in the OpenStreetMap data.  
2. Your Application should provide a REST API to get called on each ride request and get the latitude and longitude of the origin of the ride.  
3. The rate of the ride requests has a direct correlation with the demand in each district, regardless of the district area.  
4. Demand is a time-dependent concept, requests in the morning shouldn't take effect on the demand indicator in the evening, so there should be dynamic time-window, e.g., #requests in the last 10 minutes.  
5. Pricing application needs to get informed of any changes in the demand rate of districts to apply it to our price in realtime. So your application output should be constantly communicated with the pricing service.
6. Thresholds/Coefficients should be configurable, and our pricing team should be able to modify them anytime they want, take this table as a sample:


| Requests Threshold | Price Coefficient |
|--|--|
| 0 | 1 |
| 1000 | 1.05 |
| 3000 | 1.1 |
| 5000 | 1.2 |
| 10000 | 1.5 |
| 25000 | 2 |
| 50000 | 3 |


7. You're free to use any database, open-source tool, and library, but they should be dockerized. (`docker-compose.yml` should be there)  
  
You should:  
1. Design the PoC of the surge service and document your architecture briefly.  
2. Implement the service using Golang.  
3. Create a new public Github repository and push your solution to it.

**P.S:** for anything which is not specified in project specifications, you're free to decide/design.
