<span class="w-tooltip w-tooltip--left">Open menu</span>

<a href="/" class="header-default__logo-link gc-analytics-event"><img src="/images/lockup.svg" alt="web.dev" class="header-default__logo" width="125" height="30" /></a>

<a href="/learn/" class="header-default__link gc-analytics-event">Learn</a> <a href="/measure/" class="header-default__link gc-analytics-event">Measure</a> <a href="/blog/" class="header-default__link gc-analytics-event">Blog</a> <a href="/about/" class="header-default__link gc-analytics-event">About</a>

<span class="w-tooltip">Close</span>

<a href="/" class="gc-analytics-event"><img src="/images/lockup.svg" alt="web.dev" class="drawer-default__logo" width="125" height="30" /></a>

<a href="/learn/" class="drawer-default__link gc-analytics-event">Learn</a> <a href="/measure/" class="drawer-default__link gc-analytics-event">Measure</a> <a href="/blog/" class="drawer-default__link gc-analytics-event">Blog</a> <a href="/about/" class="drawer-default__link gc-analytics-event">About</a>

<img src="https://web-dev.imgix.net/image/admin/lWKSX0b7pvSUX1BDd3IH.jpg?auto=format" alt="Chrome User Experience logo, PageSpeed Insights logo, and a metrics chart." class="w-hero w-hero--cover" sizes="100vw" srcset="https://web-dev.imgix.net/image/admin/lWKSX0b7pvSUX1BDd3IH.jpg?auto=format&amp;w=200 200w,     https://web-dev.imgix.net/image/admin/lWKSX0b7pvSUX1BDd3IH.jpg?auto=format&amp;w=228 228w,     https://web-dev.imgix.net/image/admin/lWKSX0b7pvSUX1BDd3IH.jpg?auto=format&amp;w=260 260w,     https://web-dev.imgix.net/image/admin/lWKSX0b7pvSUX1BDd3IH.jpg?auto=format&amp;w=296 296w,     https://web-dev.imgix.net/image/admin/lWKSX0b7pvSUX1BDd3IH.jpg?auto=format&amp;w=338 338w,     https://web-dev.imgix.net/image/admin/lWKSX0b7pvSUX1BDd3IH.jpg?auto=format&amp;w=385 385w,     https://web-dev.imgix.net/image/admin/lWKSX0b7pvSUX1BDd3IH.jpg?auto=format&amp;w=439 439w,     https://web-dev.imgix.net/image/admin/lWKSX0b7pvSUX1BDd3IH.jpg?auto=format&amp;w=500 500w,     https://web-dev.imgix.net/image/admin/lWKSX0b7pvSUX1BDd3IH.jpg?auto=format&amp;w=571 571w,     https://web-dev.imgix.net/image/admin/lWKSX0b7pvSUX1BDd3IH.jpg?auto=format&amp;w=650 650w,     https://web-dev.imgix.net/image/admin/lWKSX0b7pvSUX1BDd3IH.jpg?auto=format&amp;w=741 741w,     https://web-dev.imgix.net/image/admin/lWKSX0b7pvSUX1BDd3IH.jpg?auto=format&amp;w=845 845w,     https://web-dev.imgix.net/image/admin/lWKSX0b7pvSUX1BDd3IH.jpg?auto=format&amp;w=964 964w,     https://web-dev.imgix.net/image/admin/lWKSX0b7pvSUX1BDd3IH.jpg?auto=format&amp;w=1098 1098w,     https://web-dev.imgix.net/image/admin/lWKSX0b7pvSUX1BDd3IH.jpg?auto=format&amp;w=1252 1252w,     https://web-dev.imgix.net/image/admin/lWKSX0b7pvSUX1BDd3IH.jpg?auto=format&amp;w=1428 1428w,     https://web-dev.imgix.net/image/admin/lWKSX0b7pvSUX1BDd3IH.jpg?auto=format&amp;w=1600 1600w" width="1600" height="480" />

## <a href="#speed-tooling-evolutions:-highlights-from-chrome-developer-summit-2019" class="w-toc__header--link">Speed tooling evolutions: highlights from Chrome Developer Summit 2019</a>

- [New performance metrics](#new-performance-metrics)
- [Largest Contentful Paint (LCP)](<#largest-contentful-paint-(lcp)>)
- [Total Blocking Time (TBT)](<#total-blocking-time-(tbt)>)
- [Cumulative Layout Shift (CLS)](<#cumulative-layout-shift-(cls)>)
- [Field data (CrUX) thresholds adjusted in PageSpeed Insights](<#field-data-(crux)-thresholds-adjusted-in-pagespeed-insights>)
- [Canonical URL redirects in PageSpeed Insights](#canonical-url-redirects-in-pagespeed-insights)
- [CrUX in the new Search Console Speed report](#crux-in-the-new-search-console-speed-report)
- [Web Almanac](#web-almanac)
- [Learn more](#learn-more)

Share <a href="/newsletter/" class="w-actions__fab w-actions__fab--subscribe gc-analytics-event"><span>subscribe</span></a>

- <a href="/" class="w-breadcrumbs__link w-breadcrumbs__link--left-justify gc-analytics-event">Home</a>
- <a href="/blog" class="w-breadcrumbs__link gc-analytics-event">All articles</a>

# Speed tooling evolutions: highlights from Chrome Developer Summit 2019

New performance metrics, updates to PageSpeed Insights and Chrome User Experience Report (CrUX), and more.

Dec 16, 2019

[<img src="https://web-dev.imgix.net/image/admin/IyB0bE6NGAvhRJkD6wRz.jpg?auto=format&amp;fit=crop&amp;h=64&amp;w=64" alt="Elizabeth Sweeny" class="w-author__image" sizes="(min-width: 64px) 64px, calc(100vw - 48px)" srcset="https://web-dev.imgix.net/image/admin/IyB0bE6NGAvhRJkD6wRz.jpg?fit=crop&amp;h=64&amp;w=64&amp;auto=format&amp;dpr=1&amp;q=75 1x,     https://web-dev.imgix.net/image/admin/IyB0bE6NGAvhRJkD6wRz.jpg?fit=crop&amp;h=64&amp;w=64&amp;auto=format&amp;dpr=2&amp;q=50 2x,     https://web-dev.imgix.net/image/admin/IyB0bE6NGAvhRJkD6wRz.jpg?fit=crop&amp;h=64&amp;w=64&amp;auto=format&amp;dpr=3&amp;q=35 3x,     https://web-dev.imgix.net/image/admin/IyB0bE6NGAvhRJkD6wRz.jpg?fit=crop&amp;h=64&amp;w=64&amp;auto=format&amp;dpr=4&amp;q=23 4x,     https://web-dev.imgix.net/image/admin/IyB0bE6NGAvhRJkD6wRz.jpg?fit=crop&amp;h=64&amp;w=64&amp;auto=format&amp;dpr=5&amp;q=20 5x" width="64" height="64" />](/authors/egsweeny/)

<a href="/authors/egsweeny/" class="w-author__name-link">Elizabeth Sweeny</a>

- <a href="https://twitter.com/egsweeny" class="w-author__link">Twitter</a>
- <a href="https://github.com/egsweeny" class="w-author__link">GitHub</a>

At Chrome Developer Summit, Paul Irish and I announced updates to Lighthouse—[Lighthouse CI, new performance score formula, and more](/lighthouse-evolution-cds-2019). Along with big Lighthouse news, we presented exciting performance tooling developments including new performance metrics, updates to PageSpeed Insights and Chrome User Experience Report (CrUX), and insights from the Web Almanac's analysis of the web ecosystem.

## New performance metrics <a href="#new-performance-metrics" class="w-headline-link">#</a>

Measuring the nuances of a user's experience is the key to quantifying the impact it has on your bottom line and tracking improvements and regressions. Over time, new metrics have evolved to capture those nuances and fill in the gaps in measuring user experience. The newest addition to the metrics story are two [field metrics](/user-centric-performance-metrics/#in-the-field)—[Largest Contentful Paint (LCP)](/lcp) and [Cumulative Layout Shift (CLS)](/cls)—which are being incubated in W3C Web Performance Working Group, and a new [lab metric](/user-centric-performance-metrics/#in-the-lab)—[Total Blocking Time (TBT)](/tbt).

### Largest Contentful Paint (LCP) <a href="#largest-contentful-paint-(lcp)" class="w-headline-link">#</a>

[Largest Contentful Paint (LCP)](/lcp/) reports the time when the largest content element becomes visible in the viewport.

Before Largest Contentful Paint, [First Meaningful Paint (FMP)](/first-meaningful-paint/) and [Speed Index (SI)](/speed-index/) served to capture the loading experience after the initial paint, but these metrics are complex and often do not identify when the main content of the page has loaded. Research has shown that simply looking at when [the largest element on the page](/lcp/#examples) is rendered better represents when the main content of a page is loaded.

The new Largest Contentful Paint metric will soon be available in Lighthouse reports and in the meantime you can [measure LCP in JavaScript](/lcp/#measure-lcp-in-javascript).

### Total Blocking Time (TBT) <a href="#total-blocking-time-(tbt)" class="w-headline-link">#</a>

[Total Blocking Time (TBT)](/tbt/) metric measures the total amount of time between [First Contentful Paint (FCP)](/first-contentful-paint/) and [Time to Interactive (TTI)](/interactive/) where the main thread was blocked for long enough to prevent input responsiveness.

A [task is considered long](/custom-metrics/#long-tasks-api) if it runs on the main thread for more than 50 milliseconds. Any millisecond over that is counted towards that task's blocking time.

<figure><img src="https://web-dev.imgix.net/image/admin/73CEd4i55qCVQKdOb6iK.png?auto=format" class="w-screenshot" sizes="(min-width: 633px) 633px, calc(100vw - 48px)" srcset="https://web-dev.imgix.net/image/admin/73CEd4i55qCVQKdOb6iK.png?auto=format&amp;w=200 200w,     https://web-dev.imgix.net/image/admin/73CEd4i55qCVQKdOb6iK.png?auto=format&amp;w=228 228w,     https://web-dev.imgix.net/image/admin/73CEd4i55qCVQKdOb6iK.png?auto=format&amp;w=260 260w,     https://web-dev.imgix.net/image/admin/73CEd4i55qCVQKdOb6iK.png?auto=format&amp;w=296 296w,     https://web-dev.imgix.net/image/admin/73CEd4i55qCVQKdOb6iK.png?auto=format&amp;w=338 338w,     https://web-dev.imgix.net/image/admin/73CEd4i55qCVQKdOb6iK.png?auto=format&amp;w=385 385w,     https://web-dev.imgix.net/image/admin/73CEd4i55qCVQKdOb6iK.png?auto=format&amp;w=439 439w,     https://web-dev.imgix.net/image/admin/73CEd4i55qCVQKdOb6iK.png?auto=format&amp;w=500 500w,     https://web-dev.imgix.net/image/admin/73CEd4i55qCVQKdOb6iK.png?auto=format&amp;w=571 571w,     https://web-dev.imgix.net/image/admin/73CEd4i55qCVQKdOb6iK.png?auto=format&amp;w=650 650w,     https://web-dev.imgix.net/image/admin/73CEd4i55qCVQKdOb6iK.png?auto=format&amp;w=741 741w,     https://web-dev.imgix.net/image/admin/73CEd4i55qCVQKdOb6iK.png?auto=format&amp;w=845 845w,     https://web-dev.imgix.net/image/admin/73CEd4i55qCVQKdOb6iK.png?auto=format&amp;w=964 964w,     https://web-dev.imgix.net/image/admin/73CEd4i55qCVQKdOb6iK.png?auto=format&amp;w=1098 1098w,     https://web-dev.imgix.net/image/admin/73CEd4i55qCVQKdOb6iK.png?auto=format&amp;w=1252 1252w,     https://web-dev.imgix.net/image/admin/73CEd4i55qCVQKdOb6iK.png?auto=format&amp;w=1266 1266w" width="633" height="292" /></figure>The Total Blocking Time for a page is the sum of the blocking times of all long tasks that occured between FCP and TTI.

<figure><img src="https://web-dev.imgix.net/image/admin/OGlrzhJ7ViNsywtZmUAh.png?auto=format" class="w-screenshot" sizes="(min-width: 800px) 800px, calc(100vw - 48px)" srcset="https://web-dev.imgix.net/image/admin/OGlrzhJ7ViNsywtZmUAh.png?auto=format&amp;w=200 200w,     https://web-dev.imgix.net/image/admin/OGlrzhJ7ViNsywtZmUAh.png?auto=format&amp;w=228 228w,     https://web-dev.imgix.net/image/admin/OGlrzhJ7ViNsywtZmUAh.png?auto=format&amp;w=260 260w,     https://web-dev.imgix.net/image/admin/OGlrzhJ7ViNsywtZmUAh.png?auto=format&amp;w=296 296w,     https://web-dev.imgix.net/image/admin/OGlrzhJ7ViNsywtZmUAh.png?auto=format&amp;w=338 338w,     https://web-dev.imgix.net/image/admin/OGlrzhJ7ViNsywtZmUAh.png?auto=format&amp;w=385 385w,     https://web-dev.imgix.net/image/admin/OGlrzhJ7ViNsywtZmUAh.png?auto=format&amp;w=439 439w,     https://web-dev.imgix.net/image/admin/OGlrzhJ7ViNsywtZmUAh.png?auto=format&amp;w=500 500w,     https://web-dev.imgix.net/image/admin/OGlrzhJ7ViNsywtZmUAh.png?auto=format&amp;w=571 571w,     https://web-dev.imgix.net/image/admin/OGlrzhJ7ViNsywtZmUAh.png?auto=format&amp;w=650 650w,     https://web-dev.imgix.net/image/admin/OGlrzhJ7ViNsywtZmUAh.png?auto=format&amp;w=741 741w,     https://web-dev.imgix.net/image/admin/OGlrzhJ7ViNsywtZmUAh.png?auto=format&amp;w=845 845w,     https://web-dev.imgix.net/image/admin/OGlrzhJ7ViNsywtZmUAh.png?auto=format&amp;w=964 964w,     https://web-dev.imgix.net/image/admin/OGlrzhJ7ViNsywtZmUAh.png?auto=format&amp;w=1098 1098w,     https://web-dev.imgix.net/image/admin/OGlrzhJ7ViNsywtZmUAh.png?auto=format&amp;w=1252 1252w,     https://web-dev.imgix.net/image/admin/OGlrzhJ7ViNsywtZmUAh.png?auto=format&amp;w=1428 1428w,     https://web-dev.imgix.net/image/admin/OGlrzhJ7ViNsywtZmUAh.png?auto=format&amp;w=1600 1600w" width="800" height="236" /></figure>While Time to Interactive does a good job of identifying when the main thread calms down later in load, Total Blocking Time aims to quantify how strained the main thread is throughout load. This way, TTI and TBT complement each other and provide balance.

### Cumulative Layout Shift (CLS) <a href="#cumulative-layout-shift-(cls)" class="w-headline-link">#</a>

[Cumulative Layout Shift (CLS)](/cls/) measures visual stability of a page and quantifies how often users experience unexpected layout shifts. Unexpected movement of content can be very frustrating and this new metric helps you address that problem by measuring how often it's occurring for your users.

A screencast illustrating how layout instability can negatively affect users.

Check out the [detailed guide to Cumulative Layout Shift](/cls) to learn how it's calculated and how to measure it.

The new Lighthouse performance score formula will soon de-emphasize FMP and FCI and include the three new metrics—LCP, TBT, and CLS—as they better capture when a page feels usable.

<figure><img src="https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/wB1bqc1tymL2uPuDgqpP.png?auto=format" class="w-screenshot" sizes="(min-width: 800px) 800px, calc(100vw - 48px)" srcset="https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/wB1bqc1tymL2uPuDgqpP.png?auto=format&amp;w=200 200w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/wB1bqc1tymL2uPuDgqpP.png?auto=format&amp;w=228 228w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/wB1bqc1tymL2uPuDgqpP.png?auto=format&amp;w=260 260w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/wB1bqc1tymL2uPuDgqpP.png?auto=format&amp;w=296 296w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/wB1bqc1tymL2uPuDgqpP.png?auto=format&amp;w=338 338w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/wB1bqc1tymL2uPuDgqpP.png?auto=format&amp;w=385 385w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/wB1bqc1tymL2uPuDgqpP.png?auto=format&amp;w=439 439w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/wB1bqc1tymL2uPuDgqpP.png?auto=format&amp;w=500 500w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/wB1bqc1tymL2uPuDgqpP.png?auto=format&amp;w=571 571w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/wB1bqc1tymL2uPuDgqpP.png?auto=format&amp;w=650 650w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/wB1bqc1tymL2uPuDgqpP.png?auto=format&amp;w=741 741w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/wB1bqc1tymL2uPuDgqpP.png?auto=format&amp;w=845 845w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/wB1bqc1tymL2uPuDgqpP.png?auto=format&amp;w=964 964w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/wB1bqc1tymL2uPuDgqpP.png?auto=format&amp;w=1098 1098w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/wB1bqc1tymL2uPuDgqpP.png?auto=format&amp;w=1252 1252w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/wB1bqc1tymL2uPuDgqpP.png?auto=format&amp;w=1428 1428w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/wB1bqc1tymL2uPuDgqpP.png?auto=format&amp;w=1600 1600w" width="800" height="375" /></figure>Check out [Lighthouse performance scoring](/performance-scoring/) and the new [web.dev metrics collection](/metrics/) to learn more.

## Field data (CrUX) thresholds adjusted in PageSpeed Insights <a href="#field-data-(crux)-thresholds-adjusted-in-pagespeed-insights" class="w-headline-link">#</a>

Over the past year we have been analyzing [web performance from the field](/user-centric-performance-metrics/#in-the-field) via [Chrome User Experience](https://developers.google.com/web/tools/chrome-user-experience-report) (CrUX) data. With insights from that data we reassessed the thresholds that we use to label a website "slow", "moderate", or "fast" in field performance.

The term "average" that used to describe sites that are in between "slow" and "fast" is now changed to "moderate" which is more fitting since this middle group was not related to a statistical average.

<figure><img src="https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/jvGzonBGrlqZD2LtzaPB.png?auto=format" class="w-screenshot" sizes="(min-width: 748px) 748px, calc(100vw - 48px)" srcset="https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/jvGzonBGrlqZD2LtzaPB.png?auto=format&amp;w=200 200w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/jvGzonBGrlqZD2LtzaPB.png?auto=format&amp;w=228 228w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/jvGzonBGrlqZD2LtzaPB.png?auto=format&amp;w=260 260w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/jvGzonBGrlqZD2LtzaPB.png?auto=format&amp;w=296 296w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/jvGzonBGrlqZD2LtzaPB.png?auto=format&amp;w=338 338w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/jvGzonBGrlqZD2LtzaPB.png?auto=format&amp;w=385 385w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/jvGzonBGrlqZD2LtzaPB.png?auto=format&amp;w=439 439w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/jvGzonBGrlqZD2LtzaPB.png?auto=format&amp;w=500 500w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/jvGzonBGrlqZD2LtzaPB.png?auto=format&amp;w=571 571w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/jvGzonBGrlqZD2LtzaPB.png?auto=format&amp;w=650 650w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/jvGzonBGrlqZD2LtzaPB.png?auto=format&amp;w=741 741w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/jvGzonBGrlqZD2LtzaPB.png?auto=format&amp;w=845 845w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/jvGzonBGrlqZD2LtzaPB.png?auto=format&amp;w=964 964w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/jvGzonBGrlqZD2LtzaPB.png?auto=format&amp;w=1098 1098w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/jvGzonBGrlqZD2LtzaPB.png?auto=format&amp;w=1252 1252w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/jvGzonBGrlqZD2LtzaPB.png?auto=format&amp;w=1428 1428w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/jvGzonBGrlqZD2LtzaPB.png?auto=format&amp;w=1496 1496w" width="748" height="200" /></figure>In order to get an overall assessment for a site, [PageSpeed Insights (PSI)](https://developers.google.com/speed/pagespeed/insights) uses a certain percentile of the total distribution of field data as the golden number for that site; the previous thresholds used were 90th percentile for First Contentful Paint and 95th percentile for First Input Delay (FID).

For example, if a site has an FCP distribution of 50% fast, 30% moderate, 20% slow, the 90th percentile FCP is in the slow section, making the overall field score for the site slow.

This has been adjusted to have a better overall distribution across websites and the new breakdown is:

<table><tbody><tr class="odd"><td>Metric</td><td>Overall Percentile</td><td>Fast (ms)</td><td>Moderate (ms)</td><td>Slow (ms)</td></tr><tr class="even"><td>FCP</td><td>75th percentile</td><td>1000</td><td>1000-3000</td><td>3000+</td></tr><tr class="odd"><td>FID</td><td>95th percentile</td><td>100</td><td>100-300</td><td>300+</td></tr></tbody></table>

For example, now if a site has an FCP distribution of 50% fast, 30% moderate, 20% slow, the 75th percentile FCP is in the moderate section, making the overall field score for the site moderate.

## Canonical URL redirects in PageSpeed Insights <a href="#canonical-url-redirects-in-pagespeed-insights" class="w-headline-link">#</a>

To enable you to measure the user's experience as accurately as possible, the PageSpeed Insights team has added a reanalyze prompt to PSI. For sites that are redirected to a new URL, you're prompted to rerun the report on the landing URL for a more complete picture of your actual performance.

## <figure><img src="https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/K299AL6Ni7dO5W4ksqXF.png?auto=format" class="w-screenshot" sizes="(min-width: 800px) 800px, calc(100vw - 48px)" srcset="https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/K299AL6Ni7dO5W4ksqXF.png?auto=format&amp;w=200 200w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/K299AL6Ni7dO5W4ksqXF.png?auto=format&amp;w=228 228w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/K299AL6Ni7dO5W4ksqXF.png?auto=format&amp;w=260 260w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/K299AL6Ni7dO5W4ksqXF.png?auto=format&amp;w=296 296w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/K299AL6Ni7dO5W4ksqXF.png?auto=format&amp;w=338 338w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/K299AL6Ni7dO5W4ksqXF.png?auto=format&amp;w=385 385w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/K299AL6Ni7dO5W4ksqXF.png?auto=format&amp;w=439 439w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/K299AL6Ni7dO5W4ksqXF.png?auto=format&amp;w=500 500w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/K299AL6Ni7dO5W4ksqXF.png?auto=format&amp;w=571 571w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/K299AL6Ni7dO5W4ksqXF.png?auto=format&amp;w=650 650w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/K299AL6Ni7dO5W4ksqXF.png?auto=format&amp;w=741 741w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/K299AL6Ni7dO5W4ksqXF.png?auto=format&amp;w=845 845w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/K299AL6Ni7dO5W4ksqXF.png?auto=format&amp;w=964 964w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/K299AL6Ni7dO5W4ksqXF.png?auto=format&amp;w=1098 1098w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/K299AL6Ni7dO5W4ksqXF.png?auto=format&amp;w=1252 1252w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/K299AL6Ni7dO5W4ksqXF.png?auto=format&amp;w=1428 1428w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/K299AL6Ni7dO5W4ksqXF.png?auto=format&amp;w=1600 1600w" width="800" height="223" /></figure>CrUX in the new Search Console Speed report <a href="#crux-in-the-new-search-console-speed-report" class="w-headline-link">#</a>

Search Console rolled out their [new Speed report](https://webmasters.googleblog.com/2019/11/search-console-speed-report.html) a week before Chrome Dev Summit. It uses data from the Chrome User Experience Report to help site owners discover potential user experience problems. The Speed report automatically assigns groups of similar URLs into "Fast", "Moderate," and "Slow" buckets, and helps prioritize performance improvements for specific issues.

## <figure><img src="https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/ny8QAjPaET6sIUX4z3Pz.png?auto=format" class="w-screenshot" sizes="(min-width: 800px) 800px, calc(100vw - 48px)" srcset="https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/ny8QAjPaET6sIUX4z3Pz.png?auto=format&amp;w=200 200w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/ny8QAjPaET6sIUX4z3Pz.png?auto=format&amp;w=228 228w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/ny8QAjPaET6sIUX4z3Pz.png?auto=format&amp;w=260 260w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/ny8QAjPaET6sIUX4z3Pz.png?auto=format&amp;w=296 296w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/ny8QAjPaET6sIUX4z3Pz.png?auto=format&amp;w=338 338w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/ny8QAjPaET6sIUX4z3Pz.png?auto=format&amp;w=385 385w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/ny8QAjPaET6sIUX4z3Pz.png?auto=format&amp;w=439 439w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/ny8QAjPaET6sIUX4z3Pz.png?auto=format&amp;w=500 500w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/ny8QAjPaET6sIUX4z3Pz.png?auto=format&amp;w=571 571w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/ny8QAjPaET6sIUX4z3Pz.png?auto=format&amp;w=650 650w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/ny8QAjPaET6sIUX4z3Pz.png?auto=format&amp;w=741 741w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/ny8QAjPaET6sIUX4z3Pz.png?auto=format&amp;w=845 845w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/ny8QAjPaET6sIUX4z3Pz.png?auto=format&amp;w=964 964w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/ny8QAjPaET6sIUX4z3Pz.png?auto=format&amp;w=1098 1098w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/ny8QAjPaET6sIUX4z3Pz.png?auto=format&amp;w=1252 1252w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/ny8QAjPaET6sIUX4z3Pz.png?auto=format&amp;w=1428 1428w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/ny8QAjPaET6sIUX4z3Pz.png?auto=format&amp;w=1600 1600w" width="800" height="801" /></figure>Web Almanac <a href="#web-almanac" class="w-headline-link">#</a>

<figure><img src="https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/lVldn64qc3gc5UDHeMBo.png?auto=format" class="w-screenshot" sizes="(min-width: 800px) 800px, calc(100vw - 48px)" srcset="https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/lVldn64qc3gc5UDHeMBo.png?auto=format&amp;w=200 200w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/lVldn64qc3gc5UDHeMBo.png?auto=format&amp;w=228 228w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/lVldn64qc3gc5UDHeMBo.png?auto=format&amp;w=260 260w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/lVldn64qc3gc5UDHeMBo.png?auto=format&amp;w=296 296w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/lVldn64qc3gc5UDHeMBo.png?auto=format&amp;w=338 338w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/lVldn64qc3gc5UDHeMBo.png?auto=format&amp;w=385 385w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/lVldn64qc3gc5UDHeMBo.png?auto=format&amp;w=439 439w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/lVldn64qc3gc5UDHeMBo.png?auto=format&amp;w=500 500w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/lVldn64qc3gc5UDHeMBo.png?auto=format&amp;w=571 571w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/lVldn64qc3gc5UDHeMBo.png?auto=format&amp;w=650 650w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/lVldn64qc3gc5UDHeMBo.png?auto=format&amp;w=741 741w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/lVldn64qc3gc5UDHeMBo.png?auto=format&amp;w=845 845w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/lVldn64qc3gc5UDHeMBo.png?auto=format&amp;w=964 964w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/lVldn64qc3gc5UDHeMBo.png?auto=format&amp;w=1098 1098w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/lVldn64qc3gc5UDHeMBo.png?auto=format&amp;w=1252 1252w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/lVldn64qc3gc5UDHeMBo.png?auto=format&amp;w=1428 1428w,     https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/lVldn64qc3gc5UDHeMBo.png?auto=format&amp;w=1600 1600w" width="800" height="450" /></figure>In the opening keynote we announced the launch of the [Web Almanac](https://almanac.httparchive.org/en/2019/), an annual project that matches the stats and trends about the state of the web with the expertise of the web community. 85 contributors, made up of Chrome developers and the web community, have volunteered to work on the project, which analyzes 20 core aspects about the web addressing how sites are built, delivered, and experienced. Start exploring the Web Almanac to learn more about the state of [performance](https://almanac.httparchive.org/en/2019/performance), [JavaScript](https://almanac.httparchive.org/en/2019/javascript), and [third-party](https://almanac.httparchive.org/en/2019/third-parties) code on the web.

## Learn more <a href="#learn-more" class="w-headline-link">#</a>

For more details about performance tooling updates from Chrome Developer Summit, watch the Speed tooling evolutions talk:

<a href="/tags/performance/" class="w-chip">Performance</a>

<span class="w-mr--sm"> Last updated: Dec 16, 2019 </span> [Improve article](https://github.com/GoogleChrome/web.dev/blob/master/src/site/content/en/blog/speed-tooling-evolutions-cds-2019/index.md)

<a href="/blog" class="w-article-navigation__link w-article-navigation__link--back w-article-navigation__link--single gc-analytics-event">Return to all articles</a>

- ### Contribute

  - <a href="https://github.com/GoogleChrome/web.dev/issues/new?assignees=&amp;labels=bug&amp;template=bug_report.md&amp;title=" class="w-footer__linkbox-link">File a bug</a>
  - <a href="https://github.com/googlechrome/web.dev" class="w-footer__linkbox-link">View source</a>

- ### Related content

  - <a href="https://blog.chromium.org/" class="w-footer__linkbox-link">Chrome updates</a>
  - <a href="https://developers.google.com/web/" class="w-footer__linkbox-link">Web Fundamentals</a>
  - <a href="https://developers.google.com/web/showcase/" class="w-footer__linkbox-link">Case studies</a>
  - <a href="https://devwebfeed.appspot.com/" class="w-footer__linkbox-link">DevWeb Content Firehose</a>
  - <a href="/podcasts/" class="w-footer__linkbox-link">Podcasts</a>
  - <a href="/shows/" class="w-footer__linkbox-link">Shows</a>

- ### Connect

  - <a href="https://www.twitter.com/@ChromiumDev" class="w-footer__linkbox-link">Twitter</a>
  - <a href="https://www.youtube.com/user/ChromeDevelopers" class="w-footer__linkbox-link">YouTube</a>

<a href="https://developers.google.com/" class="w-footer__utility-logo-link"><img src="/images/lockup-color.png" alt="Google Developers" class="w-footer__utility-logo" width="185" height="33" /></a>

- <a href="https://developer.chrome.com/home" class="w-footer__utility-link">Chrome</a>
- <a href="https://firebase.google.com/" class="w-footer__utility-link">Firebase</a>
- <a href="https://cloud.google.com/" class="w-footer__utility-link">Google Cloud Platform</a>
- <a href="https://developers.google.com/products" class="w-footer__utility-link">All products</a>

<!-- -->

- <a href="https://policies.google.com/" class="w-footer__utility-link">Terms &amp; Privacy</a>
- <a href="/community-guidelines/" class="w-footer__utility-link">Community Guidelines</a>

Except as otherwise noted, the content of this page is licensed under the [Creative Commons Attribution 4.0 License](https://creativecommons.org/licenses/by/4.0/), and code samples are licensed under the [Apache 2.0 License](https://www.apache.org/licenses/LICENSE-2.0). For details, see the [Google Developers Site Policies](https://developers.google.com/site-policies).