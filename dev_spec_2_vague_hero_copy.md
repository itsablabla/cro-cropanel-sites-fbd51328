# Vague hero copy — dev spec
Site: allbirds.com · Priority 2 · High · Effort: Low (0.5-2 days)

## Problem
The hero headline 'Wildly Comfortable. Super Natural.' is abstract and doesn't directly address the visitor's intent to find comfortable, sustainable shoes, causing them to rely on secondary copy or navigation to understand the value proposition.

## Evidence (from the live site)
> H1: 'Wildly Comfortable. Super Natural.' CTAs: 'SHOP MEN', 'SHOP WOMEN'. Body sample includes 'Wear All Day Comfort' and 'Materials From The Earth' sections below the fold.

## Current state
h1: Wildly Comfortable. Super Natural.; cta: SHOP MEN / SHOP WOMEN; notes: The headline is a brand slogan, not a value proposition. It doesn't mention shoes, comfort, or sustainability explicitly. Visitors must read secondary copy or navigate to understand what Allbirds offers.

## Required change
h1: Comfortable Shoes, Made from Natural Materials; cta: Shop Men's Shoes / Shop Women's Shoes; notes: Directly state the product and key benefits. Use CTAs that specify the product category to reduce ambiguity and guide visitors to the right collection.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Directly state the product and key benefits. Use CTAs that specify the product category to reduce ambiguity and guide visitors to the right collection.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_vague_hero_copy` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 299,882 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; not testable at current traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
