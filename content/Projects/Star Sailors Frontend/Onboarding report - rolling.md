# 16/4/24
## First rollthrough
* Sign up
* Once confirmed, redirected to index page
* Empty index with `layoutnonav`

## 23/4/24
New plan for onboarding:
1. Users will be given a random `basePlanets` entity upon signup. They are able to collect all of them, eventually, and there is no fundemental difference in difficulty as the 6 base anomalous entities are all confirmed exoplanets anyway
2. For testing, they will all be given id "3" upon signup until further notice

Users are currently being redirected to `/tests/onboarding` route after registering/signup. This is the method I want to use (however we will move this to a different route). This is where the `location` is being set (it should be done automatically in PROD), and then where the magic will begin.