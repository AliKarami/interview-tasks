# Feature Flag Platform

Sometimes we need to turn on and off a certain functionality of an application during runtime without deploying new code. A/B testing is one of the most common use-cases that can easily be done if we have customized feature flags.

In order to make this kind of experiment more straightforward, we need to have a feature flag platform that is placed beside our API Gateway that tells us which service should be active for each user.

For the first version of the feature-flag platform, we only need to support feature activation based on version and gradual release (for example, having a specific feature for only 30% of users) to be able to run A/B test experiments.

These are the project specifications:

1. Your Application should provide a REST API to have CRUD operations on feature-flag rules
2. There are four kinds of feature-flag rules:
    1. Global (which is 100% on/off for all users)
    2. Partial (which specifies the percentage of users this feature should be enabled for)
    3. Minimum version (which specifies a minimum app version that this feature should be enabled on)
    4. Combination of rules 2 and 3
3. Partial releases should be sticky for users. So if a feature is active for a specific user, it should remain active for them
4. Versions are not integers; we're using semantic versioning, so you should consider that when you're comparing if a version is higher or not
5. Your Application should provide a REST API that gets the `user_id` and `version` and returns the list of active feature flags
6. You're free to use any database, open-source tool, and library, but they should be dockerized. (`docker-compose.yml` should be present)

Examples:

| Feature           | Rule                                                 | Description                                                                                                |
|-------------------|------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
| Red Signup button | Globally on                                          | `red-signup-button` feature flag should return for all requests                                            |
| Hamburger Menu    | Partial for 10% of users                             | `hamburger-menu` feature flag should return for 10% of user ids                                            |
| 3D View           | Minimum application version 3.1.5                    | `3d-view` feature flag should return only for users that have an application that is on version 3.1.5 or higher |
| Show Traffic      | Partial for 40% of minimum application version 4.0.0 | `show-traffic` feature flag should return only for 40% of users that are using an application with version 4.0.0 or higher |

You should:
1. Design the PoC of the feature flag service and document your architecture briefly
2. Implement the service using Golang/Python
3. Create a new public Github repository and push your solution to it

**P.S:** for anything which is not specified in project specifications, you're free to decide/design.
