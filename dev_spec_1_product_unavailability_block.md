# Product Unavailability Block — dev spec
Site: allbirds.com · Priority 1 · Urgent · Effort: Medium (2-5 days)

## Problem
A product page displays a price but offers a 'Get Notified' CTA instead of an 'Add to Cart' button, indicating unavailability without clear upfront communication.

## Evidence (from the live site)
> On '/products/anytime-ankle-sock', 'prices': ['$14.00'] is present, but 'ctas': ['Get Notified'] is offered, with no 'Add to Cart' CTA.

## Current state
h1: Anytime Ankle Sock; cta: Get Notified; notes: The product page for 'Anytime Ankle Sock' shows a price of $14.00 but only offers a 'Get Notified' button, implying the product is out of stock or not yet released, without explicitly stating its status.

## Required change
h1: Anytime Ankle Sock; cta: Add to Cart (if available) / Out of Stock (if unavailable); notes: If the product is unavailable, clearly state 'Out of Stock' or 'Coming Soon' near the product title/price. If it's available, ensure an 'Add to Cart' CTA is present. Avoid leading users to a product page where they cannot complete a purchase without clear upfront messaging.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN If the product is unavailable, clearly state 'Out of Stock' or 'Coming Soon' near the product title/price. If it's available, ensure an 'Add to Cart' CTA is present. Avoid leading users to a product page where they cannot complete a purchase without clear upfront messaging.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_product_unavailability_block` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 118,817 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; 40 days

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
