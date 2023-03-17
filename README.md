<img src="/assets/logo.svg" alt="o11y.wiki" title="The Observability Wiki" height="80" width="68" />

# o11y.wiki

A glossary of all terms related to Observability, starting from A to Z! The
inspiration of this project started from the desire to understand and document
terms and concepts related to Observability at one single place.

Below document contains all the terms sorted alphabetically with their
definitions.

## A

### Alert

An alert is a notification that an incident or specific condition about the health of a system has occured, which indicates potential issues with a service or system.

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

Cardinality refers to the number of unique values in a set of data. In the context of monitoring systems, high cardinality can negatively impact performance, so it's important to manage the cardinality of metrics and labels

### Counter

As the name says, counters are used to monitor how frequently an event occurs within a program.
They help monitor metrics that increase monotonically and are exposed as time series.
For example, total requests to an API endpoint is a counter metric, it keeps increasing over time.

### CI

CI (Continuous Integration) is a practice of integrating code changes into a shared repository frequently. CI helps detect and resolve conflicts early and ensures that new code integrates smoothly with the existing codebase.

### CD

CD (Continuous Delivery) is a practice of delivering code changes to production frequently and reliably. CD aims to reduce the time between code changes and deployment, and to ensure that new code changes don't break existing functionality.

## D

### Datalake

Datalake is a single storage that stores different types of monitoring data such
as logs, metrics, traces, events. The single storage allows for far more
corelation than different data being stored at different places.

### DevOps

DevOps is a set of practices that combines software development and operations to shorten the development life cycle and improve reliability. DevOps teams use automation and collaboration to deploy software quickly and reliably.

### Downsampling

Downsampling is the process of reducing the amount of data points in a time series to make it more manageable, without losing too much detail, and can help to save storage and processing resources.

## E

### Event

An event is a significant occurrence within a system that may require attention. Events can be used to trigger alerts or notify operators of potential issues.

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

An incident refers to an unexpected event that causes a system or service to fail or degrade. Examples of incidents can include server crashes, network outages, data center failures, or security breaches.

## J

## K

### Kubernetes

Kubernetes is a popular open-source platform for managing containerized workloads and services. Kubernetes provides features for deploying, scaling, and managing containerized applications.

### KPIs

KPIs (Key Performance Indicator) are specific metrics used to track progress towards a specific goal or objective. In the context of SRE, KPIs can be used to measure the performance and reliability of a system.

## L

### Log

Logs are an record of activities performed by a system or service over a set period of time. Logs help SRE teams to track behaviours of a system. 

## M

### Metrics

Metrics are quantifiable measurement about the health of a system. They serve as KPI(Key Performance Indicators) about the health of a system or service, Metrics should be easy to understand and makes SRE teams more effective to track performance of their systems.

### Metric Life Cycle Management

Metric Life Cycle Management is the process of defining, collecting, analyzing, and acting on metrics. It's important to manage the metric life cycle to ensure that metrics are useful and provide insights into the system.

### m3DB

[m3DB](https://m3db.io/) is an open-source distributed time series database that is optimized for high cardinality and high throughput. m3DB is commonly used for storing and querying metrics in large-scale monitoring systems.

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

PromQL is a query language used to retrieve and analyze metrics from Prometheus, a popular open-source monitoring system.

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

A span is a single unit of work in a distributed system, often represented by a trace. Spans can be used to identify the performance of individual components in a system.

### Serverless

Serverless is a model where a cloud provider manages the infrastructure and automatically scales resources, allowing developers to focus on code. This model is becoming increasingly popular for building and deploying applications.

### SRE

SRE (Site Reliability Engineering) is a discipline focused on improving and maintaining the reliability of systems. SREs use a data-driven approach to manage the performance and availability of systems.

### Service Discovery

Service discovery is the process of automatically identifying and locating available services in a distributed system. Service discovery is important for managing the complexity of distributed systems.

### Samples

Samples are individual data points in a time series. Metrics are collected as samples at regular intervals and are used to analyze the behavior of a system over time.

## T

### Telemetry

Telemetry is collecting the monitoring data such as logs, metrics, and traces
from different software systems.

### Time Series

Time series is a collection of data points indexed in time order. By storing
data against successive equally spaced points in time, organizations can
understand the underlying causes of trends or systemic patterns over time.

### TSDB

TSDB stands for time-series database. TSDBs are databases optimized for timeestamp data or time-series data, which in the context of observability contains metrics about systems which are timestamped with metrics about a system or service's health.

### Trace

A trace is a detailed record of the path a request takes through a system. Traces can be used to understand the performance of a system and identify bottlenecks.

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
