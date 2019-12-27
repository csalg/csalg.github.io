---
layout: post
title: 12-Factor App A Summary
date: 2019-12-26 11:23
post-link: https://12factor.net/
---
I recently stumbled upon this methodology for building SaaS apps. The website itself is succint and to the point, but regardless here is a quick summary along with my own thoughts:

1. Track codebase in a version control system. This is the single source of truth for all deploys.
2. Declare all dependencies, completely and exactly, via a dependency declaration manifest.
3. Strict separation of config and code.
  * Use environment variables along with sane defaults. Environment variables don't require people dealing with config files.
4. Treat backing services (datastores, message/queueing systems, caching systems) as attached resources. These should be completely decoupled (basically, a microservices approach).
5. A codebase becomes a non-development deploy in three stages:
  * _Build_ (Code -> executable bundle).
  * _Release_ (Bundle + config).
  * _Run_ App runs in execution environment.
6. App should be able to scale horizontally by being executed as stateless processes. These processes share nothing and persistance is achieved by a persistence layer. This is why we need technologies like JWT.
7. Export services via port binding.
8. Concurrency (scaling by spinning out workers).
9. Disposability. Minimal startup time, graceful shutdown and robustness against sudden death are all desireable.
10. Minimize time between deploys to hours, differences between dev and production environment. Also, NoOps (developers and ops people are the same).
11. Log. What happens in STDOUT is irrelevant.
12. Admin/Management tasks are one-off processes.
