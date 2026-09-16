# System Architecture

## Project Goal

Track newsletter subscription events for **The Automation Diary** and measure conversions using Google Tag Manager (GTM), Google Analytics 4 (GA4), Google Ads, and Meta Pixel.

## Architecture Overview

Visitor opens The Automation Diary
↓
GA4 records `page_view`
↓
Visitor starts subscription form
↓
GA4 records `form_start`
↓
Visitor completes newsletter signup
↓
GA4 records `sign_up`

## Platforms Used

| Platform           | Purpose                                              |
| ------------------ | ---------------------------------------------------- |
| Substack           | Newsletter landing page and signup flow.             |
| Google Tag Manager | Hosts tracking tags and triggers.                    |
| Google Analytics 4 | Receives analytics events and validates conversions. |
| Google Ads         | Uses GA4 conversions for campaign measurement.       |
| Meta Pixel         | Tracks conversion events for Meta Ads.               |

## Verification Status

### Verified

* GTM container published in Substack.
* Google Tag configured in GTM.
* GA4 DebugView received:

  * page_view
  * scroll
  * form_start
  * sign_up
  * user_engagement

### Investigation Still Open

The custom GTM event `subscribe_click` is configured inside GTM, but GTM Preview did not reliably confirm the tag firing during Substack's authentication flow.
