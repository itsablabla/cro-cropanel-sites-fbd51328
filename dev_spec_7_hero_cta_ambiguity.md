# Hero CTA ambiguity — dev spec
Site: allbirds.com · Priority 7 · High · Effort: Medium (2-5 days)

## Problem
The hero CTAs 'SHOP MEN' and 'SHOP WOMEN' are generic and do not communicate a value proposition, reducing click-through motivation.

## Evidence (from the live site)
> The homepage hero section contains CTAs 'SHOP MEN' and 'SHOP WOMEN' with no additional context or urgency.

## Current state
h1: Wildly Comfortable. Super Natural.; cta: SHOP MEN / SHOP WOMEN; notes: CTAs are generic, no mention of new arrivals, bestsellers, or specific products.

## Required change
h1: Wildly Comfortable. Super Natural.; cta: Shop New Arrivals; notes: Use CTAs that highlight specific collections or value propositions, e.g., 'Shop New Arrivals' or 'Explore Bestsellers'.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Use CTAs that highlight specific collections or value propositions, e.g., 'Shop New Arrivals' or 'Explore Bestsellers'.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_hero_cta_ambiguity` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 299,882 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; not testable at current traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
