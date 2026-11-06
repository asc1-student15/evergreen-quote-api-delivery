# Evergreen Quote: Vision Brief

> Target length: 1 page (~300 words). Write for a Liberty Mutual VP who has 90 seconds.

## Product
**Name:** Evergreen Quote API (Phase 3 service delivery)
**Delivery week:** 3
**Delivery Lead:** Tina Matthys
**Engineering team (represented by):** https://github.com/asc1-student15/evergreen-quote-api-delivery
**GitHub Project board:** https://github.com/users/asc1-student15/projects/3

## Who is the customer?
The customer is the internal website team (REST), a partner-integration pilot (GraphQL), and the operations team. 
They need the service to be containerized, tested in a pipeline, and runnable on the company's Kubernetes platform.
The current alternative is using the sigularly deployed application, which does not use containerization.

## What pain does Evergreen Quote remove?
The new Evergreen Quote API allows our internal teams to scale their prior work from just one website into partner integrations and saves quotes that were previously lost upon restart.

## What does "good" look like at end of the week?
- Quotes are able to be saved to a database and retrieved after application restart
- Integrated partners are able to use customized fields for data entry
- Quote ids are readable strings such as `q1` so they stay easy to talk about in a review.

## What are we explicitly NOT doing this week?
- No authorization
- No real rating engine
- No multi-region story

## How will we know if it worked?
- Shippable service to include containerization, pipeline validation and active Kubernetes execution
- Three replicas behind a stable Service, plus a database, demonstrated on a local Kubernetes cluster.
