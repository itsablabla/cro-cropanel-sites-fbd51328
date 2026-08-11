# Missing H1 and description — dev spec
Site: allbirds.com · Priority 8 · High · Effort: Medium (2-5 days)

## Problem
The 'Shop All' collection page lacks an H1 and meta description, leaving visitors without a clear context for the page and hurting SEO, which can reduce organic traffic and confuse users.

## Evidence (from the live site)
> H1 count: 0. Meta description: null. Title: 'SHOP ALL '26'. Body sample starts with 'SHOP ALL '26' but no descriptive text.

## Current state
cta: Apply filters; notes: The page has no H1 and no meta description. The title 'SHOP ALL '26' is minimal and doesn't convey the breadth of products or the brand's value.

## Required change
h1: Shop All Shoes & Apparel; cta: Filter & Sort; notes: Add a descriptive H1 that includes the product categories and a meta description that highlights the range and brand promise, improving SEO and user clarity.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add a descriptive H1 that includes the product categories and a meta description that highlights the range and brand promise, improving SEO and user clarity.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_missing_h1_and_description` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 299,882 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; not testable at current traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
