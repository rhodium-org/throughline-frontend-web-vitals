# Google Web Vitals frontend performance — throughline source

This document is **generated from the graph** by `tl docs`; `tl docs --check` gates it in CI. The prose headings are hand-owned — everything between `tl:*` markers is injected from the YAML items, so the published spec can never drift from the graph.

This source re-expresses Google's **Web Vitals** performance guidance (web.dev Core Web Vitals) as a grounded IDD graph: each Core Web Vital and optimisation area is a `user_requirement`, and every individual recommendation is a `system_requirement` that `implements` its section. The guide reference lives in `attrs.source_ref`; the throughline UIDs are this source's own and immutable — a consumer cites a rule as `webvitals:SR-0001`, never by section name.

It carries
<!-- tl:count type == 'user_requirement' -->
8
<!-- tl:end --> sections and
<!-- tl:count type == 'system_requirement' -->
54
<!-- tl:end --> performance rules.

## Purpose

<!-- tl:item INT-0001 -->
**INT-0001 — Pages load fast, respond quickly and stay visually stable for real users** — `intent`, status `approved`

> Google's Web Vitals guidance exists so that a web page delivers a good real-world user experience across its whole lifecycle: it renders its main content quickly, responds promptly to user input, and does not shift about unexpectedly under the reader. These qualities are quantified by the Core Web Vitals — Largest Contentful Paint, Interaction to Next Paint and Cumulative Layout Shift — measured at the 75th percentile of page loads across mobile and desktop, so that a passing site is fast for the vast majority of its users rather than only in ideal conditions.

**source_ref**: Google Web Vitals
<!-- tl:end -->

## Core Web Vitals Thresholds

<!-- tl:item UR-0001 -->
**UR-0001 — Core Web Vitals Thresholds** — `user_requirement`, status `approved`

> The three Core Web Vitals metrics, what each measures, and the target each must meet.

*Derives from:* INT-0001

**source_ref**: Google Web Vitals: Core Web Vitals — Thresholds
<!-- tl:end -->

<!-- tl:table type == 'system_requirement' and attrs.get('source_ref', '').startswith('Google Web Vitals: Core Web Vitals — Thresholds') -->
| UID | Type | Status | Title |
|---|---|---|---|
| SR-0001 | system_requirement | approved | Keep Largest Contentful Paint at or below 2.5 seconds |
| SR-0002 | system_requirement | approved | Keep Interaction to Next Paint at or below 200 milliseconds |
| SR-0003 | system_requirement | approved | Keep Cumulative Layout Shift at or below 0.1 |
| SR-0004 | system_requirement | approved | Assess each metric at the 75th percentile across mobile and desktop |
| SR-0005 | system_requirement | approved | Measure vitals with real-user field data, not lab data alone |
<!-- tl:end -->

## Largest Contentful Paint

<!-- tl:item UR-0002 -->
**UR-0002 — Largest Contentful Paint** — `user_requirement`, status `approved`

> Rules for rendering the largest above-the-fold content element quickly (loading performance).

*Derives from:* INT-0001

**source_ref**: Google Web Vitals: Optimize LCP
<!-- tl:end -->

<!-- tl:table type == 'system_requirement' and attrs.get('source_ref', '').startswith('Google Web Vitals: Optimize LCP') -->
| UID | Type | Status | Title |
|---|---|---|---|
| SR-0006 | system_requirement | approved | Make the LCP resource discoverable in the initial HTML |
| SR-0007 | system_requirement | approved | Preload the LCP resource |
| SR-0008 | system_requirement | approved | Set fetchpriority=high on the LCP image |
| SR-0009 | system_requirement | approved | Never lazy-load the LCP image |
| SR-0010 | system_requirement | approved | Deprioritise resources that contend with the LCP resource |
| SR-0011 | system_requirement | approved | Render main content on the server |
| SR-0012 | system_requirement | approved | Optimise Time to First Byte |
| SR-0013 | system_requirement | approved | Preconnect to essential cross-origin servers |
<!-- tl:end -->

## Interaction to Next Paint

<!-- tl:item UR-0003 -->
**UR-0003 — Interaction to Next Paint** — `user_requirement`, status `approved`

> Rules for responding to user input promptly so the next frame is painted quickly (responsiveness).

*Derives from:* INT-0001

**source_ref**: Google Web Vitals: Optimize INP
<!-- tl:end -->

<!-- tl:table type == 'system_requirement' and attrs.get('source_ref', '').startswith('Google Web Vitals: Optimize INP') -->
| UID | Type | Status | Title |
|---|---|---|---|
| SR-0014 | system_requirement | approved | Break up long tasks |
| SR-0015 | system_requirement | approved | Yield to the main thread during long work |
| SR-0016 | system_requirement | approved | Run only render-critical logic before the next paint |
| SR-0017 | system_requirement | approved | Keep the DOM small |
| SR-0018 | system_requirement | approved | Avoid layout thrashing |
| SR-0019 | system_requirement | approved | Reduce input delay caused by script during load |
| SR-0020 | system_requirement | approved | Use content-visibility to defer offscreen rendering |
| SR-0021 | system_requirement | approved | Avoid rendering large amounts of HTML from JavaScript |
<!-- tl:end -->

## Cumulative Layout Shift

<!-- tl:item UR-0004 -->
**UR-0004 — Cumulative Layout Shift** — `user_requirement`, status `approved`

> Rules for keeping the page visually stable so content does not move unexpectedly.

*Derives from:* INT-0001

**source_ref**: Google Web Vitals: Optimize CLS
<!-- tl:end -->

<!-- tl:table type == 'system_requirement' and attrs.get('source_ref', '').startswith('Google Web Vitals: Optimize CLS') -->
| UID | Type | Status | Title |
|---|---|---|---|
| SR-0022 | system_requirement | approved | Set explicit width and height on images and video |
| SR-0023 | system_requirement | approved | Keep a consistent aspect ratio across responsive image variants |
| SR-0024 | system_requirement | approved | Reserve space for late-loading ads, embeds and iframes |
| SR-0025 | system_requirement | approved | Do not insert content above existing content |
| SR-0026 | system_requirement | approved | Let the user initiate loading of additional content |
| SR-0027 | system_requirement | approved | Animate with transform, not layout-triggering properties |
| SR-0028 | system_requirement | approved | Choose a font-display strategy that avoids reflow |
| SR-0029 | system_requirement | approved | Match fallback font metrics to the web font |
| SR-0030 | system_requirement | approved | Keep pages eligible for the back/forward cache |
<!-- tl:end -->

## Image and Media Optimisation

<!-- tl:item UR-0005 -->
**UR-0005 — Image and Media Optimisation** — `user_requirement`, status `approved`

> Rules for serving images and other media efficiently and without regressing the vitals.

*Derives from:* INT-0001

**source_ref**: Google Web Vitals: Image and Media
<!-- tl:end -->

<!-- tl:table type == 'system_requirement' and attrs.get('source_ref', '').startswith('Google Web Vitals: Image and Media') -->
| UID | Type | Status | Title |
|---|---|---|---|
| SR-0031 | system_requirement | approved | Serve images in modern formats |
| SR-0032 | system_requirement | approved | Compress and right-size images |
| SR-0033 | system_requirement | approved | Serve images through an image CDN |
| SR-0034 | system_requirement | approved | Provide responsive images with srcset and sizes |
| SR-0035 | system_requirement | approved | Lazy-load offscreen images |
<!-- tl:end -->

## JavaScript and Resource Loading

<!-- tl:item UR-0006 -->
**UR-0006 — JavaScript and Resource Loading** — `user_requirement`, status `approved`

> Rules for shipping, loading and executing scripts and other resources so they do not block rendering or the main thread.

*Derives from:* INT-0001

**source_ref**: Google Web Vitals: JavaScript and Resources
<!-- tl:end -->

<!-- tl:table type == 'system_requirement' and attrs.get('source_ref', '').startswith('Google Web Vitals: JavaScript and Resources') -->
| UID | Type | Status | Title |
|---|---|---|---|
| SR-0036 | system_requirement | approved | Do not add render-blocking synchronous scripts to the head |
| SR-0037 | system_requirement | approved | Load non-critical scripts with async or defer |
| SR-0038 | system_requirement | approved | Inline only very small critical scripts |
| SR-0039 | system_requirement | approved | Reduce JavaScript payload with code splitting |
| SR-0040 | system_requirement | approved | Remove unused JavaScript and CSS |
| SR-0041 | system_requirement | approved | Minify JavaScript and CSS |
| SR-0042 | system_requirement | approved | Eliminate render-blocking stylesheets |
| SR-0043 | system_requirement | approved | Inline critical CSS and defer the remainder |
| SR-0044 | system_requirement | approved | Avoid long critical request chains |
<!-- tl:end -->

## Web Font Loading

<!-- tl:item UR-0007 -->
**UR-0007 — Web Font Loading** — `user_requirement`, status `approved`

> Rules for delivering web fonts efficiently and without layout shift or invisible text.

*Derives from:* INT-0001

**source_ref**: Google Web Vitals: Web Fonts
<!-- tl:end -->

<!-- tl:table type == 'system_requirement' and attrs.get('source_ref', '').startswith('Google Web Vitals: Web Fonts') -->
| UID | Type | Status | Title |
|---|---|---|---|
| SR-0045 | system_requirement | approved | Serve fonts in WOFF2 |
| SR-0046 | system_requirement | approved | Subset fonts to the characters actually used |
| SR-0047 | system_requirement | approved | Preload critical fonts |
| SR-0048 | system_requirement | approved | Preconnect to third-party font origins |
| SR-0049 | system_requirement | approved | Declare @font-face early to enable early discovery |
| SR-0050 | system_requirement | approved | Reduce the number of font weights and styles |
<!-- tl:end -->

## Caching and Delivery

<!-- tl:item UR-0008 -->
**UR-0008 — Caching and Delivery** — `user_requirement`, status `approved`

> Rules for serving and caching resources so repeat and distant visitors get them fast.

*Derives from:* INT-0001

**source_ref**: Google Web Vitals: Caching and Delivery
<!-- tl:end -->

<!-- tl:table type == 'system_requirement' and attrs.get('source_ref', '').startswith('Google Web Vitals: Caching and Delivery') -->
| UID | Type | Status | Title |
|---|---|---|---|
| SR-0051 | system_requirement | approved | Apply an efficient Cache-Control policy to static assets |
| SR-0052 | system_requirement | approved | Fingerprint static assets to cache safely and forever |
| SR-0053 | system_requirement | approved | Compress text resources with Brotli or gzip |
| SR-0054 | system_requirement | approved | Serve resources from a CDN close to the user |
<!-- tl:end -->

