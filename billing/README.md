# RepForge Billing & Stripe Plan Design

This folder defines how billing and subscriptions should work for RepForge.  
Implementation will use **Stripe** for payments and subscription management.

RepForge is a B2B SaaS product for insurance agents and agencies.

---

## 🧾 Billing Model (V1)

### Core model:
- **Subscription-based**
- **Per seat (per agent)** with agency accounts
- Monthly recurring billing

### Two primary customer types:
1. Solo Agent
2. Agency (Admin + Multiple Agents)

---

## 💳 Stripe Products & Prices (Example Plan)

These can be adjusted later, but V1 should be built to support:

### 1. Solo Agent Plan
- Product: `repforge_solo`
- Billing: Monthly
- Price example: $79/month
- Includes:
  - 1 agent seat
  - X hours/month of audio processing included

### 2. Agency Plan
- Product: `repforge_agency`
- Billing: Monthly
- Base price example: $199/month (includes 3 seats)
- Additional Seat:
  - Product: `repforge_seat_addon`
  - Example: $49/month per extra seat

---

## 🌐 Stripe Integration Requirements

### For V1:

- Stripe Checkout or Stripe Customer Portal
- Subscription creation on signup or upgrade
- Webhook handling for:
  - `checkout.session.completed`
  - `invoice.paid`
  - `customer.subscription.updated`
  - `customer.subscription.deleted`

### Data to store in Supabase:

For each organization / solo agent:
- `stripe_customer_id`
- `stripe_subscription_id`
- Plan type (solo/agency)
- Active / inactive status
- Seats purchased
- Seats in use

---

## 👥 Seat Management

For **agency accounts**:

- Admin can:
  - Invite agents
  - Remove agents
- System must:
  - Enforce seat count limit (cannot invite more agents than seats)
  - Show “used seats” vs “available seats”

If admin wants more agents than seats:
- Redirect to “Upgrade / Manage Billing” (Stripe Customer Portal)

---

## 🔒 Access Control Based on Billing

- If subscription is **active** → full access.
- If subscription is **past_due** → warning banner, grace period (configurable).
- If subscription is **canceled** or **incomplete**:
  - Lock access to new AI processing
  - Allow read-only access to existing data

---

## 🧩 Recommended Stripe Setup

In Stripe Dashboard:
- Create Products:
  - RepForge Solo
  - RepForge Agency
  - RepForge Extra Seat
- Create Prices:
  - Monthly recurring for each

---

## 📡 Webhook Endpoint (High-Level)

A future Next.js API route (example):

- `/api/stripe/webhook`

Responsibilities:
- Verify Stripe signature
- Parse event type
- Update Supabase accordingly
- Log events for debugging

---

## 🎯 V1 Billing Success Criteria

- A new customer can:
  - Start a subscription via Stripe
  - Return to RepForge with an active account

- Admin can:
  - Manage seats
  - Keep usage within paid limits

- System can:
  - Automatically react to subscription changes via Stripe webhooks

This document defines the billing and Stripe model so developers can implement payments correctly and predictably.
