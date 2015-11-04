---
layout: kb
title:  "Librato - Getting Started"
date:   2015-11-03 21:51:00
categories: kb
---


[Source](http://support.metrics.librato.com/knowledgebase/articles/61566-librato-getting-started "Permalink to Getting Started – Customer Feedback &amp; Support for Librato")

# Getting Started – Customer Feedback &amp; Support for Librato

This article covers our new Spaces UI. If you're looking for a primer on our legacy metrics UI, click [here][1].&nbsp;

From a very high level, this is the Librato workflow:

* You send **Metrics** to our API.
* You use our UI to create a **Space**, add a new&nbsp;**Chart,&nbsp;**﻿and assign one or more of your metrics to it.&nbsp;
* You add other charts to the space and arrange them to suit your needs.
Quick intro / demo of Librato.

## After first signing up: Spaces

When you log in to Librato for the first time you won't have any pre-defined spaces. Make your first space by clicking the&nbsp;_﻿Create a new Space&nbsp;_﻿button. &nbsp;Then you can give the space a name, and begin adding charts to it. &nbsp;

![][2]  

## Getting metrics into Librato

Before you can add data to a chart you need to begin emitting metric data to our API. You can emit metrics to Librato from every open source collection agent out there, as well as directly from any popular programming language via a native language binding. You can even ship metrics to us straight from the command line with our shell client, or CURL. &nbsp;You'll find a comprehensive list of agents and bindings on the [product page][3] of our marketing site.

No matter what combination of collection agents you choose, you'll need to provide your Librato API Token. &nbsp;You can get a copy of your API token via the&nbsp;_﻿account settings&nbsp;_﻿menu in the upper left hand side of Spaces.&nbsp;  

![][4]

## Metrics and Sources

Librato is a hosted telemetry system for time-series data. You POST key/value pairs along with a timestamp to our API, and we take care of storage, and provide awesome visualization and alerts.&nbsp;

Librato's notion of a _﻿metric_﻿&nbsp;might be a little different than what you may be used to.&nbsp;We use a two dimensional namespace that separates metric names, and source names. The metric name refers to the variable you are measuring, like _﻿CPU Load,&nbsp;_﻿or&nbsp;_﻿Thread Count. _﻿The source name usually refers to the instance you are taking the measurement from, like _﻿Server Name,&nbsp;_﻿or the name of the Application or Service. Separated from the metric name, the source name&nbsp;is a very powerful filtering tool which, as we'll see further down, makes it easier to build charts and seamlessly visualize short-lived entities like threads and jobs.&nbsp;  

To add a new chart to the space, click the plus sign in the upper right-hand corner, and select the type of chart you'd like to add (Don't worry, you can change the chart type later).&nbsp;

![][5]  

## Charts

A few seconds after you send a measurement to our API, the metric will appear in the metrics list in the chart editor. Simply check it to add it to the chart.&nbsp;

![][6]

When you first add the metric to a chart, it'll default to displaying the average of all the sources that are reporting that particular metric.&nbsp;If you'd like to see each source individually you can change the source summarization to "breakout".&nbsp;

![][7]

## Broken out, the chart will display one line for each source name you're emitting. &nbsp;

![][8]  

## You can filter the individual sources with the&nbsp;_﻿source name&nbsp;_﻿field. By default this field is set to&nbsp;_﻿Dynamic.&nbsp;_﻿We'll see what that means in a moment.&nbsp;

## Spaces

Spaces our primary user interface. You can create as many Spaces&nbsp;as you want, and use them to present charts that depict related metrics. At Librato, for example, we have a Space for each service that we run in our micro-services infrastructure. All charts in a space automatically refresh, and mousing over a chart will pop-up a tool-tip legend and cursor-tracking line, which makes it easy to correlate events and data across every chart in the space.

&nbsp;![][9]

At the top of the space you'll notice a date-range selector and rwd/pause/fwd buttons which you can use to explore back in time, or pause the charts at a particular day/time range. If any of the charts in a space are configured to use&nbsp;_﻿Dynamic_﻿ sources, the space will also have a field for you to enter a dynamic source.&nbsp;

![][10]

Every chart in the space that is configured to use dynamic sources will reflect the typeglob entered in this field. &nbsp;If, for example, you are using server-names as the source, and your naming convention is type-ID-env (eg web-14-prod), you can use the dynamic source field to quickly show you all the production data by entering *prod* in the dynamic source field.&nbsp;

Alerts

We believe that [Alerts][11] are a fundamental component of a monitoring service. You can create alerts for any metric you send to Librato.&nbsp;

For more details please read the [Alerts section][11].

![][12]  

## Bookmarking and Sharing

Our URI's always include unique query parameters i.e. 'source', 'duration', and (in the case of custom date ranges) 'end_time', which makes it easy to bookmark your favorite Spaces, and craft links that specify specific date ranges et al.&nbsp;If you want to share a chart or space with a [collaborator][13] just send them the URI and they will see exactly what you see.

If you want to share a chart or space with an external entity, or embed a chart in a chat service like Slack, you can use our snapshot feature, which allows you to seamlessly snapshot and send straight from our UI.&nbsp;

![][14]  

* * *

Have questions or feedback? Use the&nbsp;"Contact support" or "Give feedback" links on this page.  
Don't have a Librato account? [Sign up][15] for a free 30 day trial.

[1]: http://support.metrics.librato.com/knowledgebase/articles/537559-librato-the-legacy-ui
[2]: https://librato.uservoice.com/assets/78531865/Screen%20Shot%202015-04-06%20at%2012.15.03%20PM.png
[3]: https://www.librato.com/product/collection-agents
[4]: https://librato.uservoice.com/assets/78532984/Screen%20Shot%202015-04-06%20at%2012.34.01%20PM.png
[5]: https://librato.uservoice.com/assets/78546892/Screen%20Shot%202015-04-06%20at%202.58.13%20PM.png
[6]: https://librato.uservoice.com/assets/78535480/Screen%20Shot%202015-04-06%20at%201.13.25%20PM.png
[7]: https://librato.uservoice.com/assets/78536062/Screen%20Shot%202015-04-06%20at%201.30.40%20PM.png
[8]: https://librato.uservoice.com/assets/78536302/Screen%20Shot%202015-04-06%20at%201.35.03%20PM.png
[9]: https://librato.uservoice.com/assets/78537853/Screen%20Shot%202015-04-06%20at%201.52.04%20PM.png
[10]: https://librato.uservoice.com/assets/78538486/Screen%20Shot%202015-04-06%20at%202.06.43%20PM.png
[11]: http://support.metrics.librato.com/knowledgebase/articles/332379-introduction-to-librato-alerts
[12]: https://librato.uservoice.com/assets/77374214/alerts2.png
[13]: http://support.metrics.librato.com/knowledgebase/articles/50921-how-do-i-give-other-people-access-to-my-metrics-ac
[14]: https://librato.uservoice.com/assets/78539425/Screen%20Shot%202015-04-06%20at%202.17.54%20PM.png
[15]: https://metrics.librato.com/?utm_campaign=Uservoice%20Sign%20Up&amp;utm_medium=UserVoice&amp;utm_source=Website#signup
  