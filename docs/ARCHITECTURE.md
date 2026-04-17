# Orbit Marketplace · Architecture Notes

**Product:** Orbit Marketplace
**Platforms:** iOS and Android, native mobile apps
**Dates:** January 2014 to August 2019

This document sketches the high-level architecture of Orbit as a two-sided marketplace product. It describes the surfaces and their relationships at a product-engineering level. Specific technology choices, infrastructure details, and implementation specifications are not reproduced here.

---

## Two-sidedness

Orbit had the standard marketplace structure: supply (sellers posting listings), demand (buyers browsing and transacting), and a set of shared services connecting the two.

```
┌──────────────────────────────────────────────────────────────┐
│                         Mobile clients                        │
│                    iOS (native) · Android (native)            │
└──────────────────────────┬───────────────────────────────────┘
                           │
                           ▼
┌──────────────────────────────────────────────────────────────┐
│                        Backend services                      │
│                                                              │
│    Users &        Listings &      Discovery      Messaging   │
│    profiles       catalog         & search       & chat      │
│                                                              │
│                         Ratings                              │
└──────────────────────────────────────────────────────────────┘
```

---

## Service responsibilities at a high level

**Users and profiles.** Identity, @username reservation, follower and following relationships, profile metadata (photo, display name, bio).

**Listings and catalog.** Product listings with images, price, title, description, seller ownership, and location. Listing lifecycle states (active, sold, deleted).

**Discovery and search.** The surface that powers both the orbit visualization and the grid feed. Takes the user's location context and returns nearby listings and sellers. This is the area covered by the patent application filed through Foley and Hoag (see `PATENT_AND_TRADEMARK.md`).

**Messaging and chat.** Listing-scoped conversation threads between buyer and seller. Supports free-form messages and the Request to Buy action as a structured signal.

**Ratings.** Two-sided rating records tied to completed transactions. Aggregate rating is surfaced on the user profile.

---

## Two-sidedness as a product reality

Supply liquidity and demand density were the two gating constraints on any hyperlocal marketplace. The product was launched market by market (four markets total), which made supply density a per-launch concern rather than a per-user-signup concern.

---

## Scope note

This is a high-level product-engineering sketch. Internal implementation details, schemas, infrastructure choices, and scaling specifics are intentionally not reproduced in this public document.
