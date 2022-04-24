
# Referral

The referral is one of the most successful marketing strategies to earn more customers. We define some incentives for people who invite their friends to register in our application.

We need to build a system to facilitate this process for us. Each user has a user_id in the database, and we need to give each user a referral code and give a prize to them once a new user registers in our system via their referral code.

These are the project specifications:

1. Your application should provide a REST API that returns the referral code of a user by getting her user_id
2. Referral code of a user is constant, and each user has only one referral code
3. Your application should provide a REST API for submitting a referral by getting a new user's id and a referral code.
4. You should prevent fraud. Each user can submit only one referral code
5. Each time a referral gets submitted, the user who refers the new user will get rewarded with some referral points
6. Your application should provide a REST API to return the total points of a user collected by the referral platform by getting her user id
7. To encourage users to refer more people in this system, we give them rewards in the Fibonacci order:

| Number of Refers | Reward    |
|------------------|-----------|
| 1                | 1 point   |
| 2                | 1 point   |
| 3                | 2 points  |
| 4                | 3 points  |
| 5                | 5 points  |
| 6                | 8 points  |
| 7                | 13 points |
| ...              | ...       |
8. You're free to use any database, open-source tool, and library, but they should be dockerized. (`docker-compose.yml` should be there)

You should:
1. Design the PoC of the referral service and document your architecture briefly.
2. Implement the service using Golang.
3. Create a new public Github repository and push your solution to it.

**P.S:** for anything not specified in project specifications, you're free to decide/design.
