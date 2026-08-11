# Free shipping threshold hidden — dev spec
Site: allbirds.com · Priority 5 · High · Effort: Low (0.5-2 days)

## Problem
The homepage hero promotes 'Wildly Comfortable. Super Natural.' without mentioning the $100 free shipping threshold, which is only disclosed in the sitewide banner, potentially causing cart abandonment at checkout.

## Evidence (from the live site)
> Hero copy: 'Wildly Comfortable. Super Natural.' while the sitewide banner states 'Free ground shipping on orders over $100'.

## Current state
h1: Wildly Comfortable. Super Natural.; cta: SHOP MEN / SHOP WOMEN; notes: No mention of shipping threshold or any pricing transparency in hero.

## Required change
h1: Wildly Comfortable. Super Natural. Free Shipping Over $100; cta: SHOP MEN / SHOP WOMEN; notes: Add a subheadline or badge indicating free shipping threshold to set expectations early.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add a subheadline or badge indicating free shipping threshold to set expectations early.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_free_shipping_threshold_hidden` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 299,882 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; not testable at current traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
