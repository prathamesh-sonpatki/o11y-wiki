<img src="/assets/logo.svg" alt="o11y.wiki" title="The Observability Wiki" height="80" width="68" />

![GitHub last commit](https://img.shields.io/github/last-commit/prathamesh-sonpatki/o11y-wiki?style=flat-square) [![Open Source Helpers](https://www.codetriage.com/prathamesh-sonpatki/o11y-wiki/badges/users.svg)](https://www.codetriage.com/prathamesh-sonpatki/o11y-wiki) ![Discord](https://img.shields.io/discord/900280171762942012)

# o11y.wiki

A glossary of all terms related to Observability, starting from A to Z! The
inspiration for this project started from the desire to understand and document terms and concepts related to Observability in one single place.

The below document contains all the terms sorted alphabetically with their definitions.

## A

### Active Time Series
Active Time Series is relevant in the case of Time Series databases as it often decides billing. A time series is considered active if the TSDB scraped new data for it recently. Prometheus provides `prometheus_tsdb_head_series` metric, which shows the number of active time series. What is *recent* is mostly decided by the TSDB but we can consider 30 minutes as the window for active time series calculation.


### Alert

An alert is a trigger that a specific change in a system's health has occurred, which indicates potential issues.
An alert will result in a notification to the system operators so that they can take further actions to remediate or fix the issues.

### APM

APM, or Application Performance monitoring, is a software tool that measures and
tracks an application's performance. It helps understand answers related to how the
application is performing in real time.

### Alertmanager

The [Alertmanager](https://prometheus.io/docs/alerting/latest/alertmanager/) is
a component used with Prometheus that handles alerts sent by client applications
such as the Prometheus server. It takes care of deduplicating, grouping, and
routing them to the correct receiver integration, such as email, PagerDuty, or
OpsGenie. It also takes care of silencing and inhibition of alerts.

## B

## C

### Cardinality

Cardinality refers to the number of unique attributes of a metric. E.g., for a metric that tracks
no. of requests to an HTTP service, the attributes such as the user's email can explode the unique
combinations of the metric because each user's email will result in a unique [time series](#time-series).
High cardinality can result in latent dashboards because it causes querying of data slow due to higher
computation and memory overhead.

### Counter

As the name says, counters monitor how frequently an event occurs within a program.
They help monitor metrics that increase monotonically and are exposed as time series.
For example, total requests to an API endpoint are a counter metric increasing over time.

### CI

CI (Continuous Integration) integrates code changes into a common branch of a shared repository and runs automated tests against it every time the changes are merged or a commit is made. It allows for detecting issues in the code faster because it is tested continuously, as the name says.

### CD

CD (Continuous Delivery) is the practice of delivering code changes to production frequently and reliably. An example would be using GitHub Actions to run tests via CI, prepare a docker image for the app once the tests pass, and then trigger the deployment via CD.

## D

### Data lake

Datalake is a single storage that stores different types of monitoring data, such
as logs, metrics, traces, and events. Single storage allows for far more
correlation than data stored at different places.

### DevOps

DevOps is a set of practices that combines software development and operations to shorten the development life cycle and improve reliability. The idea behind the DevOps movement is to reduce silos between different teams and make software delivery faster and more reliable via automation and collaboration.

### Downsampling

Downsampling reduces the data points in a time series to make it more manageable without losing the essence. It can reduce the cost of storage and the performance of querying.

### DPM(Data Points Per Minute)

Data Point is a unique metric occurrence with a timestamp, value, and labels. The Timestamp and value are unique, as labels can also be common at other timestamps. The Data Point is also known as [sample](#/?id=samples). Data Points Per Minute is the rate of Data Points sent to a TSDB. A DPM of 1 is considered as standard. You can lower it to ship more samples as needed.
## E

### Event

Events are hard to define because everything is an event, but let us give it a try 😉. An event is primarily a change event that can mean a pod restart, deployment, or configuration flag change. Events are important because they affect the system's state externally and can help correlate incidents with metrics, traces, and logs.

### Error budget

An error budget is a predefined allowance or limit for acceptable errors or failures within a system or process. It represents the tolerance for mistakes, bugs, or downtime that can occur before the user experience or overall system reliability is compromised. The error budget provides a clear, objective metric that determines how unreliable the service is allowed to be within a single quarter. This metric removes the politics from negotiations between the SREs and the product developers when deciding how much risk to allow.

### Exporter

An exporter is a component that collects and transforms metrics data from a specific system or format into a standardized format that can be consumed by monitoring systems. Examples of exporters include Prometheus exporters and OpenTelemetry exporters.

## F

### FinOps

FinOps is a practice that combines financial and operational management to optimize cloud spending. Finops teams use data-driven approaches to manage cloud costs and improve ROI.

## G

### Gauge

Gauges periodically measure a metric or take a snapshot at a specific moment.
A gauge's value is not ever-increasing; it can increase or decrease over time.
An example of a gauge metric is CPU percentage, which will change over time, either increasing
or decreasing.

### Gateway

A gateway is a component that acts as an entry point for traffic from external sources into a system. In the context of observability, gateways can be used to manage traffic routing, load balancing, and security.

## H

### Histogram

In statistics, a histogram is a graphical representation of the data distribution.
In the context of Observability, histograms are the metrics that represent the distribution
of data in specific buckets. Latency can be an excellent example of a histogram metric.

## I

### Instrumentation

Instrumentation is the process of improving an application's monitoring and tracing capabilities by adding code to specific functions or points in the codebase. Using language-specific instrumentation libraries, this entails writing logic that generates logs, events, or adds timers to functions and other telemetry data. The goal of instrumentation is to make it easier to observe and measure the performance of an application, as well as to detect and diagnose errors. Instrumentation allows developers and operators to gain insights into an application's behaviour and flow by collecting and analysing telemetry data. There are two types of instrumentation available in general.

* Auto Instrumentation: There are intelligent agents available that attach to your application and extract telemetry data, requiring no code changes.

* Manual Instrumentation: As stated in the definition, it requires someone to add code to the application to begin and end a trace, span and define the payload, and add logs. It makes use of instrumentation client libraries and SDKs, which are available for a variety of programming languages.

OpenTelemetry, Zipkin instrumentation libraries are examples.

### Incident

An incident is an unexpected event that causes a system or service to fail or degrade. Examples of incidents can include service degradation, downtimes, server crashes, network outages, data center failures, or security breaches.

### InfluxDB

InfluxDB is an open-source time-series database developed by the company InfluxData. It is designed to store large volumes of time series data and quickly perform real-time analysis on that data. It has its query language InfluxQL. It can be used with Grafana as a visualization tool.

## J

## K

### Kubernetes

Kubernetes is a popular open-source platform for managing containerized workloads and services. Kubernetes provides features for deploying, scaling, and managing containerized applications.

### KPIs

KPIs (Key Performance Indicators) track progress toward a specific goal or objective. In the context of o11y, KPIs can be used to measure the performance and reliability of a system, such as response times, failure rates, or peak load.

## L

### Log

Logs record activities a system, service, or tool performs over time. They are easy to adopt but run into standardization challenges because different tools and languages can have different logging patterns. Logs can overgrow but are extremely important for debugging a problem once identified.

### Latency

Latency is an expression of how much time it takes for a data packet to travel from one designated point to another. Ideally, latency will be as close to zero as possible.
High latency decreases communication bandwidth, and can be temporary or permanent, depending on the source of the delays. Latency is measured in milliseconds, or during speed tests, it's referred to as a ping rate.

### Lag

Lag is a slang term for a noticeable decrease in application speed, due to extreme network congestion or insufficient processing power. 
When traffic is heavier than network capacity, the network requires that a program wait before sending or receiving data.

## M

### Metrics

Metrics are quantifiable measurements of the health of a system. They are the fastest and cheapest way to understand the system's health. They are aggregated data, giving a bird's eye view of the system's performance. An example of a metric is the throughput of an API or latency.

### Metric Life Cycle Management

Metric Life Cycle Management defines, collects, analyzes, and acts on metrics. This involves creating a pipeline of metrics that moves from ingestion, storage, query, and alerting stages. It allows operations such as dropping unused data, performing streaming aggregates, and providing control over how and who can query specific data and define alerting.

### m3DB

[m3DB](https://m3db.io/) is an open-source distributed time series database optimized for high cardinality and throughput. m3DB is commonly used for storing and querying metrics in large-scale monitoring systems. It originated at Uber.

### MTTD

MTTD (Mean Time to Detect) is the average time it takes to identify that an incident has occurred. It is an important metric because the faster an incident is detected, the faster it can be resolved.

### MTBI

MTBI (Mean Time Between Incidents) measures the average time between incidents. A high MTBI indicates that the system is reliable and stable.

### MTTR

MTTR (Mean Time to Recover/Resolve) is the average time to recover or resolve an incident. A low MTTR indicates that the system is resilient and can recover quickly from incidents.

### Monitoring 

Monitoring is collecting and analyzing data about a system from outside based on the data that the system outputs. In observability terminology, monitoring is sometimes also restricted to metrics management.

## N

## O

### Observability

Observability is the ability to understand the internal state of a system based on its external outputs. Observability is achieved by collecting and analyzing telemetry data, including metrics, logs, and traces.

### o11y

o11y stands for Observability!

The "11" in the middle stems from software engineering conventions that shorten
long words by substituting middle letters with the number of middle letters
instead. Like, a11y stands for accessibility.

### OpenMetrics

[OpenMetrics](https://openmetrics.io/) is a standard aimed at evolving the Prometheus exposition format. It supports text representation and Protocol Buffers and brings it into an Internet Engineering Task Force (IETF) standard. It supports both pull and push-based data collection.

### OpenCensus

[OpenCensus](https://opencensus.io/) is a collection of libraries from different languages for collecting and exporting metrics and trace data from applications. It is merged along with OpenTracing into OpenTelemetry.

### OpenTelemetry

[OpenTelemetry](https://opentelemetry.io/) is a set of open-source libraries and tools for collecting, processing, and exporting telemetry data from applications. It provides a vendor-neutral, standard way of collecting observability data and can be integrated with various systems.

## P

### Playbook

Playbooks are a set of instructions about how to respond to an alert. They include
debugging suggestions and possible actions to take to mitigate the alert.

### Prometheus

[Prometheus](https://prometheus.io/) is an open-source systems monitoring and
alerting toolkit originally built at SoundCloud.

### PromQL

PromQL is a query language that retrieves and analyzes metrics from Prometheus, a popular open-source monitoring system. It is like SQL but for time series data. A lot of other time series databases, such as [VictoriaMetrics](https://victoriametrics.com/) and [Levitate](https://last9.io/products/levitate/), are also PromQL compatible.

### Platform Engineering

Platform engineering is designing, implementing, and maintaining software platforms that support other applications and services. Platforms can include infrastructure, tools, and services used by other teams in the organization.

## Q

## R

### Runbook

A runbook is a document that provides step-by-step instructions for executing routine tasks or procedures. Runbooks are used to standardize and automate standard operational procedures.

### RED

RED stands for Rate, Error, and Duration, the three key metrics that can help
monitor any service.

- Rate - The number of requests the service is handling
- Error - The number of failed requests
- Duration - The amount of time each request takes

### Reliability

Reliability is hard to define, but it can be termed as the quality of software
system to be trustworthy and predictable in its performance and user experience.

### Resiliency

Resiliency is the ability to avoid or mitigate impact from an adverse event by quickly responding to, and fully recovering after, a failure. 
A focus on resiliency typically amounts to an emphasis on high availability. This allows for increased uptime.

### Recovery

Recovery is the ability to restore service when failure occurs. 
Recovery is essential to strong resilience. Recovery directly impacts Recovery Time Objective (RTO), the time duration for an application to return to normal service levels after a failure, and Recovery Point Objective (RPO), the tolerance to data loss in terms of time duration. 
A focus on recovery typically leads to a well founded understanding of both design time and runtime dependencies due to the need to determine recovery methods for all possible failure points.

### RCA

Root cause analysis (RCA) is the process of finding and analyzing the causes of a problem or an event impacting the value delivery of an application or an organization. 
RCA can find one or more root causes underlying a problem needing to be addressed to solve and prevent the problem from recurring.

### RUM

Real User Monitoring (RUM) collects data about how real users interact with the system by mimicking an end user. RUM gives insights into a user's issues while using the application or system.

## S

### Span

A span is a single unit of work in a distributed system and a primary building block of distributed tracing. A trace represents a user request or a transaction in distributed tracing. Traces are broken down into multiple spans. For example, a function call to authenticate a user during a request can be represented by a span.

### Serverless

Serverless is a deployment model where a cloud provider manages the infrastructure and automatically scales resources, allowing developers to not worry about managing servers.

### SRE

SRE (Site Reliability Engineering) is a discipline focused on improving and maintaining the reliability of systems. SREs use a data-driven approach to manage the performance and availability of systems.

### Service Discovery

Service Discovery is automatically identifying and locating available services in a distributed system. Service Discovery is essential for managing the complexity of distributed systems because of the dynamic and ephemeral nature of the systems.

### Samples

Samples are individual data points in a time series. Metrics are collected as samples at regular intervals and are used to analyze the behavior of a system over time. Many time series databases use samples as billing metrics.

### SLA

A Service-Level Agreement(SLA) is a commitment between a service provider and a customer. Particular aspects of the service – quality, availability, responsibilities – are agreed between the service provider and the service user.

### SLO

A Service-Level Objective(SLO) is a key element of a SLA between a service provider and a customer. SLOs are agreed upon as a means of measuring the performance of the Service Provider and are outlined as a way of avoiding disputes between the two parties based on misunderstanding.

### SLI

A Service-Level Indicator (SLI) is anything that can be precisely measured to assist you in thinking about, defining, and determining if you are satisfying SLOs and SLAs. They are commonly presented as the ratio of the number of excellent occurrences to the total number of events. 
A simple example would be the number of successful HTTP requests divided by the total number of HTTP queries. SLIs are typically stated as a percentage, with 0 indicating that everything is broken and 100 indicating that everything is operating flawlessly.
Some of the most common types of SLIs are Availability, Latency, Error Rate and Throughput.

### Severity

Incident Severity Levels are a measurement of the impact an incident has on the business. Classifying the Severity of an issue is critical to decide how quickly and efficiently problems get resolved. There are 4 recognized Severity levels.
Level 1 – Critical Impact/System Down. Complete system outage.
Level 2 – Significant Impact/Severe downgrade of services.
Level 3 – Minor impact/Most of the system is functioning properly.
Level 4 – Low Impact/Informational.

### Scaling

A service is said to be scalable if, as resources are added to the system, it results in increased performance in a manner proportional to resources added. An always-on service is said to be scalable if adding resources to facilitate redundancy does not result in a loss of performance.
Two main ways an application can scale include vertical scaling and horizontal scaling. Vertical scaling (scaling up) increases the capacity of a resource, for example, by using a larger virtual machine (VM) size. Horizontal scaling (scaling out) adds new instances of a resource, such as VMs or database replicas.

### Saturation

The term Saturation determines how "full" your service is. The type of application that you're monitoring is directly related to the utilization metrics that you use to determine saturation. 
Saturation is the most challenging signal to implement. You need utilization metrics and the utmost flexibility to determine saturation.

### Service

A [Service](https://last9.io/blog/services-not-server-observability/) is a software component or system providing specific functions to other applications or users. 
A service can be
- Combination of endpoints that fall under the purview of a payment team.
- A piece of code catering to the Reconciliation workflow.
- A demographic-based Personal Information Collector.
- A data warehouse catering to the API and Billing teams.

Or A combination of all of the above.

### Summary

A summary is a Prometheus metric type that can be used for that can be used to monitor latencies (or other distributions like request sizes). They are similar to Histograms. However, unlike histograms, they give you the exact quantile values instead of estimates. They work best when you need the same latency value, such as P99, and do not want to avoid going through the hassles of setting histogram buckets.

### Sidecar

A sidecar is a container that runs alongside an application container and provides additional functionality, such as monitoring or service discovery. Sidecars can be used to separate cross-cutting concerns and simplify application development.

### StatsD

StatsD is a daemon for collecting and aggregating metrics data. It is often used in conjunction with monitoring systems like Graphite or Prometheus. StatsD was originally written at [Etsy](http://www.etsy.com/) and released with a [blog post](https://codeascraft.etsy.com/2011/02/15/measure-anything-measure-everything/) about how it works and why we created it.

## T

### Telemetry

Telemetry is collecting the monitoring data such as logs, metrics, and traces
from different software systems.

### Time Series

Time series is a collection of data points indexed in time order. By storing
data against successive equally spaced points in time, organizations can
understand the underlying causes of trends or systemic patterns over time.

### TSDB

TSDB or Time Series Databases are software systems for storing and retrieving time series data. Time series data are measurements or events that are tracked, monitored, downsampled, and aggregated over time.

### Trace

A trace is the complete journey of a request or workflow as it moves from one part of the system to another. It is achieved by adding a standard trace id as the request/action flows through all the hops.

### Tail Sampling

Tail sampling is a technique for collecting metrics data from the slowest requests in a system. This can be useful for understanding the causes of tail latency and identifying performance bottlenecks.

### Tail Latency

Tail latency refers to the latency of the slowest requests in a system. Tail latency is an important metric to monitor, as it can have a significant impact on the user experience and overall system performance.

### Telegraf

[Telegraf](https://www.influxdata.com/time-series-platform/telegraf/) is a server-based agent for collecting and sending all metrics and events from various data sources. It provides plugins for input, process, aggregate and output functions of telemetry data.

## U

### USE

USE stands for Utilization Saturation and Errors.

- Utilization: the average time the resource was busy servicing work
- Saturation: the degree to which the resource has extra work which it cannot service, often queued
- Errors: the count of error events

Check https://www.brendangregg.com/usemethod.html for more details.


## V


## W

## X

## Y

## Z

# FAQs

1. I want to add a new addition to the Glossary. How should I do it?

   - Please send a pull request to this
     [GitHub repository](https://github.com/prathamesh-sonpatki/o11y-wiki).

2. What is considered part of the Observability Glossary?

   - Any term or concept related to Observability, Reliability, and Monitoring of Software Systems.

---

# Thanks

This Glossary is sponsored by [Last9](https://last9.io).

<a href="https://last9.io"><img src="https://last9.github.io/assets/email-logo-green.png" alt="" loading="lazy" height="40px" /></a>
