Developing with the [RingCentral Call Log API resource](https://developers.ringcentral.com/api-docs/latest/index.html#!#RefCallLogInfo.html) is one of the most popular topics among [RingCentral Developers](https://developer.ringcentral.com).

The RingCentral Call Log is the source of truth for how extensions within your [RingCentral Account](https://service.ringcentral.com) have used RingCentral for making and receiving: Voice Calls, SMS messages, and Fax messages. Every inbound and outbound call, SMS, or fax attempted using RingCentral is recorded at the **Extension** level (meaning for each user extension in your RingCentral account) into the Call Log database.

## Non-Programmatic Ways to Access Call Log Data

Occassionally, while developing an application or integration, it is helpful for Developers to be able to test or invaliate data they are seeing using Call Log data. The training content contained in this document describes how Developers can use the [RingCentral API](https://developer.ringcentral.com/api-explorer) to access and view Call Log API resource data. You can use one of the following methods to access this data as well:

1. [Login to your RingCentral Online Account](http://success.ringcentral.com/articles/RC_Knowledge_Article/Logging-in-to-your-RingCentral-account) to [view Call Activity Log information](http://success.ringcentral.com/articles/RC_Knowledge_Article/Activity-Log-Overview) for your RingCentral extension or RingCentral Account.
2. [Accessing Call Data on your RingCentral Mobile Application](http://success.ringcentral.com/articles/en_US/RC_Knowledge_Article/5122)
3. [Use the RingCentral Desktop Application](http://success.ringcentral.com/articles/en_US/RC_Knowledge_Article/7244) to view Call Log data.

## Common Use Cases

Call Log data can be used as a solution for several use cases, the most common use cases for Call Log data by developers are:

* **Downloading** - Call Log Data to an External Database** Since RingCentral does not store Call Log data indefinitely (see [Call Log Data Retention](data-retention.md)), using the Call Log API to download or transfer Call Log data into customer-owned, long-term, persistent storage has been a very common use case.
* **Reporting** - Developers can also achieve this use case by implementing downloaded Call Log data into their persistent storage. Application developers who do not need long-term data storage have opted to use the Call Log data to power short-term reporting pages.
* **Dashboards** - Polling a RingCentral account Call Log data at a set interval of time (that is not real-time) can provide insights into performance of a team or call center.
* **CRM Integration** - Developers who need to populate interaction records into history for contacts in your CRM can leverage Call Log data when not using real-time solutions.
* **Billing Systems** - Developers who need to provide contact-specific data for time-based billing can leverage RingCentral Call Log data to populate this information on an hourly or daily basis with greater confidence.
* **Reconciliations** - Confirming if messages of a particular type were received or sent to a contact are made easy using the RingCentral Call Log data.

### Call Log Anti-Patterns

It is also important to understand anti-patterns of using Call Log, these are ways developers should **not** use this resource.

* **Real-time, or near-real-time reporting** - The Call Log API resource is labeled as a "Heavy" usage plan. RingCentral offers better solutions for event-driven, real-time (or near-real-time) reporting of what the various Extensions in your RingCentral account are doing at any given time: [Webhooks]() and/or [Push Notifications]() are the two recommended solutions.
* **Long-Polling** - While this is highly related to the above anti-pattern, it is important to clearly note that long-polling Call Log (executing multiple HTTP requests to simulate real-time, socket-based data) is not a supported use case.
