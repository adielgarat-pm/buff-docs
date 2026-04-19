# BUFF Pricing Strategy

_Working document — April 19, 2026_

---

## Guiding Principles

1. **Value First** — Parent gets real value for free, falls in love with the product, then pays for upgrades.
2. **Clear Separation** — Free vs Premium should be a sharp, predictable line. No quotas or confusing limits.
3. **Simple Pricing** — One price per family. No complicated tiers.

---

## Free vs Premium

| Feature | Free | Premium |
|---|---|---|
| Basic Missions + Rewards | ✅ | ✅ |
| Up to 2 children | ✅ | ✅ (unlimited) |
| Stickers and Boosts | ✅ | ✅ |
| Timetable — Excel | ✅ | ✅ |
| Timetable — Photo (OCR) | ❌ | ✅ |
| Smart Bag Prep | ❌ | ✅ |
| AI-personalized age-appropriate missions | ❌ | ✅ |
| Advanced Insights & reports | ❌ | ✅ |
| Personalized rewards | ❌ | ✅ |

---

## Recommended Pricing

Launch with two options only:

- **Monthly:** $9.99 / ₪29.90
- **Annual (50% savings):** $59.99 / ₪179 (effectively $5/month)

> **Important:** Show the annual option first on the paywall screen, with a "Best Value" tag. Research shows this increases annual conversion to 30-40%.

### Why $9.99 (not $4.99 or higher)

- **$4.99** — Too cheap. ADHD parents pay hundreds for therapies. Low price signals "cheap app" and drives low LTV.
- **$15+** — Too high a psychological barrier for first-time payers.
- **$9.99** — Below the $10 threshold, signals serious product, leaves room for future increases.

### Benchmark — Joon (main competitor)

Joon charges **$12.99/month** or **$89.99/year** for a similar ADHD gamification app with less functionality (no timetable, no bag prep). Our $9.99 is **intentionally under Joon** as a differentiator.

---

## Free Trial

**Length:** 14 days — SaaS industry standard, balances urgency with chance to see value.

- Parent starting onboarding automatically gets 14 days of premium
- No credit card required upfront (RevenueCat supports trial-without-payment-method)
- One day before trial end — push notification: _"1 day left! Itai completed 47 missions this month 🎯"_

---

## Conversion Targets

| Metric | Target |
|---|---|
| Trial-to-paid conversion | 8% |
| Annual vs monthly mix | 35% annual |
| Monthly churn after payment | < 8% |

Industry benchmark for parent/family apps with trial: 5-12% conversion.

---

## Geographic Pricing

RevenueCat supports per-region pricing automatically.

| Region | Monthly | Annual |
|---|---|---|
| USA | $9.99 | $59.99 |
| Israel | ₪29.90 | ₪179 |
| Europe | €8.99 | €54.99 |
| UK | £7.99 | £49.99 |

---

## Founding Members — Launch Special

The first 100 families get a **Founding Member** badge — 50% off for 2 years.

- **Monthly:** $4.99 (half of $9.99)
- **Annual:** $29.99 (half of $59.99)

This creates urgency, word-of-mouth, and early social proof.

**Mechanism:** Unique promo codes per family (BUFF001-BUFF100). Manually managed in RevenueCat backend.

---

## RevenueCat Implementation Notes

- **Products:** `buff_monthly`, `buff_annual`
- **Single entitlement:** `premium` (unlocks all gated features)
- **Trial logic:** `introductoryOffer` in RevenueCat — 14 days for each product
- **Promo codes:** For Founding Members and future campaigns

---

## Action Plan

### Before May 1
- [ ] Define products in Google Play Console + App Store Connect
- [ ] Configure `premium` entitlement in RevenueCat
- [ ] Wrap OCR + Bag Prep features with `isPremium` check
- [ ] Design Paywall Screen with annual-first + clear value explanation

### After Launch
- [ ] Track conversion rate per day of trial (day 1, 7, 13, 14)
- [ ] A/B test pricing after first 100 conversions
- [ ] Adjust based on data

---

## Notes

This is a **living document** — will be updated based on market data. Decisions in sections 3 and 4 deserve A/B testing after 200-500 active users.
