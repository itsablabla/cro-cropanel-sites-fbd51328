# Conditional Shipping Cost Clarity — dev spec
Site: allbirds.com · Priority 4 · High · Effort: Medium (2-5 days)

## Problem
The default shipping cost for orders under the free shipping threshold is not clearly stated on the landing page prior to cart interaction.

## Evidence (from the live site)
> The 'body_sample' on '/' states 'Free ground shipping on orders over $100'. However, the 'Added to Cart' section later reveals 'Shipping $5.00' for orders not meeting this threshold.

## Current state
h1: Wildly Comfortable. Super Natural.; cta: N/A; notes: Free shipping is advertised for orders over $100. A $5.00 shipping cost is revealed in the 'Added to Cart' summary for orders below this threshold, but not explicitly stated upfront on the main page.

## Required change
h1: Wildly Comfortable. Super Natural.; cta: N/A; notes: Clearly state the standard shipping cost (e.g., '$5.00 flat rate shipping on orders under $100') alongside the free shipping offer on the homepage, perhaps in the header or a prominent banner, to ensure full transparency before cart engagement.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Clearly state the standard shipping cost (e.g., '$5.00 flat rate shipping on orders under $100') alongside the free shipping offer on the homepage, perhaps in the header or a prominent banner, to ensure full transparency before cart engagement.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_conditional_shipping_cost_clarity` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 299,882 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; not testable at current traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
