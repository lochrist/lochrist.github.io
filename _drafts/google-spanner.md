---
layout: post title: "Roguelikes"
date: 2017-04-04 tags: [google, dev, spanner]
---

Nice [article](https://futurism.com/4-googles-spanner-is-now-available-on-the-cloud-for-everyone/) by Futurism on [Google Cloud Spanner](https://cloud.google.com/spanner/) the new Relational Database that is used by all big Google Services (Gmail, adWords, Photos and Play Store).

The article describes True Time, the technology Google uses to synchronize all databases transactions in all their data centers. 

> To solve this problem, Google’s engineers developed a unique timekeeping technology called TrueTime. The engineers equipped all of Google’s data centers with GPS receivers and atomic clocks, and each center would shuttle its time readings to a master server. Those servers would constantly trade their readings with other servers to produce a common time for all data centers. “This gives you faster-than-light coordination between two places,” Peter Mattis, a former Google engineer, explained to Wired.

When you read about something like this and you see the sentence: *faster-than-light coordination* you understand how good programming and good hardware can truly defy logic and makes a workflow sounds like magic.