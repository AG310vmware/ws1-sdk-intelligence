---
layout: page
title: Network Insights
hide:
  #- navigation
  - toc
---

Whenever an app makes a network call, Workspace ONE Intelligence SDK monitors and captures certain information automatically. You can optionally configure filtering and location details. For an introduction, see [Network Insights](../../dev-centre/ws1-intel/core-capabilities.md#hnetwork-insights-overview).

When Network Insights is enabled, the performance of HTTP traffic generated by either `java.net.HttpURLConnection` or `OkHttp` will be monitored. No action is needed in order to turn on Network Performance Monitoring. Simply initialize Workspace ONE Intelligence SDK as normal.

## Filtering Captured Data

By default, all URLs are stripped of query parameters before being sent to Workspace ONE Intelligence. For example the URL `www.yoururl.com/login?secret=foobar` would be reported as `www.yoururl.com/login`. It is also possible to add url blacklists to completely prevent sensitive URLs from being sent to Workspace ONE Intelligence. See [CrittercismConfig](crittercism-config.md) for further information.

## Blacklisting URLs

URL blacklisting can be used to prevent sensitive URLs from being captured by the network instrumentation. Use [CrittercismConfiguration.setURLBlacklistPatterns()](crittercism-config.md#seturlblacklistpatterns-patterns) for configuring URLs that should not be monitored by Workspace ONE Intelligence SDK. This configuration option must be set at initialization time of Workspace ONE Intelligence.

Updating the Location
Network Insights can tie location information to network data, if the application provides the location. By default, location information is not obtained by Workspace ONE Intelligence SDK.

You can update location information by using the [Crittercism.updateLocation (Location)](crittercism.md#updatelocation-curlocation) method.

## Further Readings

- [Logging Network Request](crittercism.md#logging-network-request)
- [Network Insights Best Practices](https://www.apteligent.com/developer-resources/network-insights-best-practices/)