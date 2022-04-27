# Voucher Platform

Vouchers or coupons are one of the marketing team's primary tools for customer acquisition purposes.

We need to build a system to facilitate this process for our marketing team. We should provide an application that helps them create vouchers with intended constraints and then provide APIs to check voucher availability and use vouchers in the application.

These are the project specifications:

1. There are two types of voucher:
   1. Individual Voucher: which is only usable for a specific user
   2. Global Voucher: which is usable for all users
2. Each voucher can be:
   1. Endless: can always be used regardless of the number of times it got used
   2. Count-limited: it can be used `N` times for each user
   3. Date-limited: it can be used till a specified UNIX timestamp once
3. Your Application should provide a REST API to have CRUD operations on vouchers and their constraints
4. Your Application should provide a REST API to check if a voucher is available for a specific user (based on user_id)
5. Your Application should provide a REST API to use a voucher by a specific user (based on user_id)
6. You're free to use any database, open-source tool, and library, but they should be dockerized (`docker-compose.yml` should be present)


You should:
1. Design the PoC of the voucher platform service and document your architecture briefly
2. Implement the service using Golang/Python
3. Create a new public Github repository and push your solution to it

**P.S:** For anything not specified in project specifications, you're free to decide/design.
