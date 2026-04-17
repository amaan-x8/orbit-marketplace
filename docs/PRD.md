# Orbit Marketplace · Product Reference

**Product:** Orbit Marketplace
**Platforms:** iOS and Android
**Dates:** January 2014 to August 2019
**Role:** Founder and Product Lead

This document describes the product as it shipped, reconstructed from surviving screenshots and materials. It captures the surfaces and flows that are directly observable in the product artifacts.

---

## 1. What Orbit was

A social, hyperlocal peer-to-peer marketplace for iOS and Android where users bought and sold with people nearby. The product combined a proximity-based discovery model, profile-driven seller identity, and a two-sided messaging and transaction flow.

The in-product tagline on the discovery surface reads: "Search for items being sold near you."

---

## 2. Navigation

The app uses a five-tab bottom navigation:

- **Discover** (default tab, with the orbit visualization as the primary view)
- **Wishlist**
- **Store**
- **You**
- **Chat**

---

## 3. Surfaces observed in the product

### 3.1 Discover: orbit view

The default Discover view presents a concentric-ring visualization: the user's own avatar at the center, with nearby sellers arranged in rings around them. Avatars appear around the rings and represent discoverable sellers in the surrounding area. The header includes a "DISCOVER FEED" label with a compass-style icon.

### 3.2 Discover: grid feed

A grid feed view of listings nearby. Two tabs at the top: **Following** and **Discover**. Tiles display a product photo, a blue price-overlay block in the top-left, and the product title in the bottom-left. Grid is three columns wide.

### 3.3 Profile

Every user has a profile with:

- Circular profile photo
- 5-star rating display (ratings are sourced from completed transactions, applied by both buyer and seller)
- A three-stat strip: **Products**, **Followers**, **Following**
- Display name and unique **@username** handle
- Follow button (state-aware)
- Store Products grid preview (leading into the full Store surface)

### 3.4 Store

The seller's full inventory. A two-column product grid. Each tile shows:

- Product image
- Price overlay (blue, top-left)
- Product title (bottom-left)
- NEW badge (green, top-right) on fresh listings

Top of the Store surface displays the seller's profile photo, display name, and @username. Grid/list view toggle on the top right.

### 3.5 Chat

In-app messaging scoped to a specific listing. The thread header displays the listing title. Each thread includes a **Request to Buy** action, surfaced as a structured button in the chat, used by buyers to send a formal intent to transact rather than a free-text message.

### 3.6 Home / launch

Branded home screen with the Orbit logomark, a search entry point, and the five-tab bottom nav.

---

## 4. Core flows

### 4.1 Discovery

1. User opens the app, lands on Discover
2. Orbit visualization renders nearby sellers as avatars in concentric rings
3. User can tap an avatar to open that seller's Store, or switch to the grid feed for a listings-first view

### 4.2 Transaction intent

1. User taps a listing, opens the product detail
2. User taps to message the seller, opening a Chat thread scoped to that listing
3. User can send free-form messages or a formal Request to Buy
4. Seller accepts or declines
5. On acceptance, the two parties coordinate meetup inside the thread

### 4.3 Rating loop

Ratings are contributed by both buyer and seller after a completed transaction. A user's visible star rating on their profile reflects the aggregate of these two-sided ratings.

---

## 5. Identity and trust

- **@username** is the user's permanent, unique handle
- **Star rating** is a transaction-weighted signal, visible on every profile
- **Follow graph** (followers and following counts on every profile) provides a social layer on top of commerce

---

## 6. What is not captured in this document

Specific technical implementation details, data schemas, server architecture, ranking parameters, and engineering specifications are not included here. This document describes the user-facing product based on observable artifacts only.
