<img src="/assets/logo.svg" alt="o11y.wiki" title="The Observability Wiki" height="80" width="68" />

# o11y.wiki

A glossary of all terms related to Observability, starting from A to Z! The
inspiration of this project started from the desire to understand and document
terms and concepts related to Observability at one single place.

Below document contains all the terms sorted alphabetically with their
definitions.

## A

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

### Counter

As the name says, counters are used to monitor how frequently an event occurs within a program.
They help monitor metrics that increase monotonically and are exposed as time series.
For example, total requests to an API endpoint is a counter metric, it keeps increasing over time.

## D

### Datalake

Datalake is a single storage that stores different types of monitoring data such
as logs, metrics, traces, events. The single storage allows for far more
corelation than different data being stored at different places.

## E

## F

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

## J

## K

## L

## M

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

## T

### Telemetry

Telemetry is collecting the monitoring data such as logs, metrics, and traces
from different software systems.

### Time Series

Time series is a collection of data points indexed in time order. By storing
data against successive equally spaced points in time, organizations can
understand the underlying causes of trends or systemic patterns over time.

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
