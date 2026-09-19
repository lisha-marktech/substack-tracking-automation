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
* GA4 DebugView received the following events during testing:

  * `page_view`
  * `scroll`
  * `form_start`
  * `sign_up`
  * `user_engagement`
* Google Ads conversion goal configured as **Sign-ups**.

### Investigation Outcome

A custom GTM event named `subscribe_click` was configured in Google Tag Manager.

During testing:

* GA4 DebugView received a `sign_up` event after completing the Substack signup flow.
* GTM Preview did not confirm that the custom `subscribe_click` tag fired.
* Therefore, the custom GTM event remains **unverified** and is not used as evidence for this project.

### Current Tracking Flow

The verified conversion event for this project is `sign_up`, as observed in GA4 DebugView during the newsletter signup flow.
