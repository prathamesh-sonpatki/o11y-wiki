<img src="/assets/logo.svg" alt="o11y.wiki" title="The Observability Wiki" height="80" width="68" />

# o11y.wiki

A glossary of all terms related to Observability, starting from A to Z! The
inspiration of this project started from the desire to understand and document
terms and concepts related to Observability at one single place.

Below document contains all the terms sorted alphabetically with their
definitions.

## A

### Alert

An alert is a trigger that a specific change in the health of a system has occured, which indicates potential issues. 
An alert will result into a notification to the system operators so that they can take further actions to remediate or fix the issues.

### APM

APM or Application Performance monitoring is a software tool which measures and
tracks application’s performance. It helps understand answers related to how the
application is performing in real time.

### Alertmanager

The [Alertmanager](https://prometheus.io/docs/alerting/latest/alertmanager/) is
a component used with Prometheus that handles alerts sent by client applications
such as the Prometheus server. It takes care of deduplicating, grouping, and
routing them to the correct receiver integration such as email, PagerDuty, or
OpsGenie. It also takes care of silencing and inhibition of alerts.

## B

## C

### Cardinality

Cardinality refers to the number of unique attributes of a metric. Eg. for a metric which tracks
no. of requests to an HTTP service, the attributes such as user's email can explode the unique 
combinations of the metric because each user's email will result into a unique [time series](#time-series).
High cardinality can result into latent dashboards because it causes querying of data slow due to higher
computation and memory overhead.

### Counter

As the name says, counters are used to monitor how frequently an event occurs within a program.
They help monitor metrics that increase monotonically and are exposed as time series.
For example, total requests to an API endpoint is a counter metric, it keeps increasing over time.

### CI

CI (Continuous Integration) integrates code changes into a common branch of a shared repository and runs automated tests against it every time the changes are merged, or a commit is made. This allows for detecting issues in the code faster because it is tested continuously, as the name says.

### CD

CD (Continuous Delivery) is the practice of delivering code changes to production frequently and reliably. An example would be using GitHub Actions to run tests via CI, prepare a docker image for the app once the tests pass, and then trigger the deployment via CD.

## D

### Datalake

Datalake is a single storage that stores different types of monitoring data such
as logs, metrics, traces, events. The single storage allows for far more
corelation than different data being stored at different places.

### DevOps

DevOps is a set of practices that combines software development and operations to shorten the development life cycle and improve reliability. The idea behind the DevOps movement is to reduce silos between different teams and make software delivery faster and more reliable via automation and collaboration.

### Downsampling

Downsampling is the process of reducing the amount of data points in a time series to make it more manageable without losing the essence and can help reduce the cost of storage and performance of querying. 

## E

### Event

Events are hard to define because everything is an event, but let's give it a try 😉. An event is primarily a change event that can mean a pod restart, deployment, or configuration flag change. Events are important because they affect the system's state externally and can help correlate incidents with metrics, traces, and logs.

## F

### FinOps

FinOps is a practice that combines financial and operational management to optimize cloud spending. Finops teams use data-driven approaches to manage cloud costs and improve ROI.

## G

### Gauge

Gauges periodically measure a metric or take a snapshot at a specific moment.
A gauge's value is not ever-increasing; it can go up or down over time.
An example of a gauge metric is CPU percentage, which will change over time either increasing
or decreasing.

## H

### Histogram

In statistics, a histogram is a graphical representation of the distribution of data.
In the context of Observability, histograms are type of metrics that represent distribution
of data in specific buckets. Latency can be good example of a histogram metric.

## I

### Incident

An incident is an unexpected event that causes a system or service to fail or degrade. Examples of incidents can include service degradation, downtimes, server crashes, network outages, data center failures, or security breaches.

## J

## K

### Kubernetes

Kubernetes is a popular open-source platform for managing containerized workloads and services. Kubernetes provides features for deploying, scaling, and managing containerized applications.

### KPIs

KPIs (Key Performance Indicators) track progress toward a specific goal or objective. In the context of o11y, KPIs can be used to measure the performance and reliability of a system, such as response times, failure rates, or peak load.

## L

### Log

Logs record activities a system, service, or tool performs over a set time. They are easy to adopt but run into standardization challenges because different tools and languages can have different logging patterns. Logs can grow quickly but are extremely important for debugging a problem once identified.

## M

### Metrics

Metrics are quantifiable measurements of the health of a system. They are the fastest and cheapest way to understand the health of the system. They are aggregated data essentially giving a bird's eye view of the system performance. An example of a metric is the throughput of an API or latency.

### Metric Life Cycle Management

Metric Life Cycle Management defines, collects, analyzes, and acts on metrics. This essentially involves creating a pipeline of metrics that moves from ingestion, storage, query, and alerting stages. You can drop unused data, perform streaming aggregates, and provide control over how and who can query specific data and define alerting.

### m3DB

[m3DB](https://m3db.io/) is an open-source distributed time series database that is optimized for high cardinality and high throughput. m3DB is commonly used for storing and querying metrics in large-scale monitoring systems. It was originated at Uber.

### MTTD

MTTD (Mean Time to Detect) is the average time it takes to identify that an incident has occurred. It's an important metric because the faster an incident is detected, the faster it can be resolved.

### MTBI

MTBI (Mean Time Between Incidents) measures the average time between incidents. A high MTBI indicates that the system is reliable and stable.

### MTTR

MTTR (Mean Time to Recover/Resolve) is the average time it takes to recover or resolve an incident. A low MTTR indicates that the system is resilient and can recover quickly from incidents.

## N

## O

### o11y

o11y stands for observability!

The “11” in the middle stems from software engineering conventions that shorten
long words by substituting middle letters with the number of middle letters
instead. Like, a11y stands for accessibility.

## P

### Playbook

Playbooks are a set of instructions about how to respond to an alert. They include
debugging suggestions and possible actions to take to mitigate the alert.

### Prometheus

[Prometheus](https://prometheus.io/) is an open-source systems monitoring and
alerting toolkit originally built at SoundCloud.

### PromQL

PromQL is a query language that retrieves and analyzes metrics from Prometheus, a popular open-source monitoring system. It is like SQL but for time series data. A lot of other time series databases, such as [VictoriaMetrics](https://victoriametrics.com/), and [Levitate](https://last9.io/products/levitate/) are also PromQL compatible.

### Platform Engineering

Platform engineering is the design, implementation, and maintenance of software platforms that support other applications and services. Platforms can include infrastructure, tools, and services that are used by other teams in the organization.

## Q

## R

### RED

RED stands for Rate, Error, and Duration the three key metrics that can help
monitor any service.

- Rate - The number of requests the service is handling
- Error - The number of failed requests
- Duration - The amount of time each request takes

### Reliability

Reliability is hard to define but it can be termed as the quality of software
system to be trustworthy and predictable in its performance and user experience.

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

Samples are individual data points in a time series. Metrics are collected as samples at regular intervals and are used to analyze the behavior of a system over time. A lot of time series databases use samples as billing metric.

## T

### Telemetry

Telemetry is collecting the monitoring data such as logs, metrics, and traces
from different software systems.

### Time Series

Time series is a collection of data points indexed in time order. By storing
data against successive equally spaced points in time, organizations can
understand the underlying causes of trends or systemic patterns over time.

### TSDB

TSDB or Time Series Databases are software systems are built for storing and retrieving time series data. Time series data are measurements or events that are tracked, monitored, downsampled, and aggregated over time.

### Trace

A trace is the complete journey of a request or workflow as it moves from one part of the system to another. It is achieved by adding a common trace id as the request/action flows through all the hops.

## U

### USE

USE stands for Utilization Saturation and Errors.

- Utilization: the average time the resource was busy servicing work
- Saturation: the degree to which the resource has extra work which it can't service, often queued
- Errors: the count of error events

Check https://www.brendangregg.com/usemethod.html for more details.


## V

## W

## X

## Y

## Z

# FAQs

1. I want to add a new addition to the Gloassry, how should I do it?

   - Please send a pull request to this
     [GitHub repository](https://github.com/prathamesh-sonpatki/o11y-wiki).

2. What is considered as part of Observability Glossary?

   - Any term or concept related to Observability.

---

# Thanks

This glossary is sponsored by [Last9](https://last9.io).

<a href="https://last9.io"><img src="https://last9.github.io/assets/email-logo-green.png" alt="" loading="lazy" height="40px" /></a>
