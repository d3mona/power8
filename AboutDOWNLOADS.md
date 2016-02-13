# <font color='red'>WARNING! This project has been migrated to <a href='https://github.com/AgentMC/power8/wiki/AboutDOWNLOADS'>GitHub</a> </font> #
# Introduction #

In the beginning of 2014 Google deprecated Downloads feature on .Googlecode.com

Senseless, criticized and inefficient, it was their decision, anyway.
This page is how to get **latest** version of Power8.

# Details #

## The latest version available is 1.5.5. See links below. ##

The [Downloads](https://code.google.com/p/power8/downloads/list) page won't contain all latest releases now. Last one available _there_ is 1.4.4. Instead, **you should use links from within this page**, which will always point to latest build, and a previous one.

# Links #
|<b>Status</b>|<b>Type</b>|<b>Version</b>|<b>Link</b>|<b>Changelog</b>|
|:------------|:----------|:-------------|:----------|:---------------|
|Latest       |MSI        |1.5.5.838     |[Download](http://power8.googlecode.com/svn/filez/Power8_v.1.5.5.838.msi)|[Read](https://code.google.com/p/power8/wiki/Changelog#Version_1.5.5_Beta_(v.1.5.5.838):_01.12.2014)|
|Latest       |7z         |1.5.5.838     |[Download](http://power8.googlecode.com/svn/filez/Power8_v.1.5.5.838.7z)|[Read](https://code.google.com/p/power8/wiki/Changelog#Version_1.5.5_Beta_(v.1.5.5.838):_01.12.2014)|
|Pre-Latest   |MSI        |1.5.4.817     |[Download](http://power8.googlecode.com/svn/filez/Power8_v.1.5.4.817.msi)|[Read](https://code.google.com/p/power8/wiki/Changelog#Version_1.5.4_Beta_(v.1.5.4.817):_09.10.2014)|
|Pre-Latest   |7z         |1.5.4.817     |[Download](http://power8.googlecode.com/svn/filez/Power8_v.1.5.4.817.7z)|[Read](https://code.google.com/p/power8/wiki/Changelog#Version_1.5.4_Beta_(v.1.5.4.817):_09.10.2014)|


# Sources #
The 7zipped source of the latest version is available [here](http://power8.googlecode.com/svn/filez/Power8_src.7z).

# Older versions #
  * Versions up to 1.4.4 are available under legacy [Downloads page](https://code.google.com/p/power8/downloads/list?can=1);
  * Other versions after 1.4.4 are available in [this](http://code.google.com/p/power8/source/browse/#svn%2Ffilez) folder. Current version will be stored directly in this folder, older releases will be stored in folder Old, and there's also folder for special builds, that you should NOT usually touch.

# Auto-update #
Auto-update feature should work just like before. From it's point of view nothing changed at all actually.

# Statistics tracing #
Previously we used simple and straightforward approach involving built-in Googlecode's analytics binding. Along with the number of downloads of certain versions, this provided us required statistics to analyze usages and trends.

Unfortunately, the downloads feature was deprecated and we have to use other ways to analyze spreading of Power8, the target audience and the download count. For this, starting with 1.4.5, we send http requests to Google analytics service:
  * When application is updated;
  * When application is successfully launched.
The requests (so-called "events") contain only "ping" itself and bear no other user information. Data we receive is:
  * The event itself - Deploy or Startup in our case;
  * Country of user launching Power8 - calculated by Google automatically based on IP. Power8 doesn't collect this information;
  * Power8 version & OS version - sent by Power8. Only pure version string (e.g. Windows NT 6.3.x.x) is sent, no other information is shared;
  * Language chosen by the system to present the Power8 UI to you. It may not be user language or some system setting, but rather most appropriate locale selected based on system interface UI.
This is safe because:
  * We do not send any user-, computer-, domain- or network-specific information;
  * We send data over encrypted connection (https);
  * The content has length of two-three hundred BYTES so it won't affect your traffic plan;
  * Statistics reporting is completely independent from Power8 engine, application will not disturb you with errors if the reporting fails;
  * You can simply view data being sent by installing network scanner like Fiddler and use it to see the request Power8 sends on startup.

# Exceptions tracing #
Starting from 1.5.0 we also send all exceptions to Google Analytics which should help us to identify and fix problems. For example, release 1.5.1 already contains couple of fixes for most "popular" errors. 1.5.3 introduced the 75+% bugs demolition and new auto-tracing technology for complicated cases. Overall, you should experience much LESS crashes starting from 1.5.3.

For errors detected by Power8, we send only it type for statistics. For _unhandled_ exceptions we also send the error message and the stack trace. An unhandled exception is the error which Power8 is not expecting, so after it occurs, Power8 will crash. Right before such crashes we send data to Google Analytics. The data usually includes no user-specific information and contains barely the description of what happened, where in the program it happened and why it happened. However in the next releases we plan to provide the checkbox to disable this extended information reporting.

As for now, below you can find the chart on how this helped to improve the Power8 stability during last several months.

![https://power8.googlecode.com/svn/wiki/P8Stable.png](https://power8.googlecode.com/svn/wiki/P8Stable.png)

Here you can find 2 rows:
  * <font color='#5B9BD5'><b>Deployment stability</b></font> is calculated as (total number of launches-total number of crashes)/(total number of launches) during 3 days. It demonstrates whether the release has critical bugs, and if not - how many percent of Power8 starts were finished successfully. 3 days are there because according to statistics this is the term where most of active users (30% of all users) are updated. After 3 days there are more updates of course, but the number per day drops significantly and so stops being representative.
  * <font color='#ED7D31'><b>Runtime stability</b></font> is little bit different. It is calculated as (total number of users-users that met crash)/(total number of users) during 30 days. Power8 is a complicated application and interacts with the operating system on different levels and by different means. And while the deployment stability above mostly shows Power8 stability itself, this row shows the "real life" behavior where there are more than just the application itself. Also 30 days gives us 10 times more probability to get rare errors. That's why it has lower stability factor.

You may notice that there's no 1.5.1 version shown. This is so because it contained critical reporting bug and was active for about 24 hours. Also, you can see a stability drop in 1.5.4. This is caused by a nasty bug introduced in this version which affected some amount of users having specific removable drives attached.