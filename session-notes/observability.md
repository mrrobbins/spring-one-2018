# Observability 3 Ways: Logging, Metrics, Tracing

@adrianfcole and Jon Schneider

Tues 2PM

https://springoneplatform.io/2018/sessions/observability-with-spring-based-distributed-systems

## Intro

- "Hope is not a course of action." - Sergeant, US Army
- Used thermal binoculars, PSP, and a composite video cable to detect roadside projectiles.
- Unifying theory: Everything is based on events - coda hale

# Awareness

- Alert on max, performance tune to high percentiles.
  - Max response time *is* being experienced by your user.
  - Focus on improving for high majority of your users in your code. You have more control than tuning for outliers like garbage collection.

# Performance Logging

- Log at microsecond. Don't make granular decisions based on log timestamps coming from servers with NTP shift variance.

`long span = TimeUnit.NANOSECONDS.toMillis(System.nanoTime() - startNs)`

# Tracing

- Sidecar
  - aka "buddy" or "mesh"
  - Use a service mesh to trace around your services
  - Observability of things entering and exiting the container
  - Good for applications you don't control, can't directly change
- Agent
  - JVM agents
  - Technique used by APM tools
  - Similar to sidecar, can only detect things it has been reconfigured to do
