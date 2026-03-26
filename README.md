# QuickClear: Automated Fast-Auction Marketplace

**QuickClear** is a production-ready, mobile-first auction platform for second-hand movable goods. Built with a "Vinted meets eBay Live" aesthetic, it utilizes AI-driven verification and automated escrow to provide a high-trust, low-friction bidding environment.

## 🚀 Platform Overview
QuickClear removes human intervention from the auction process through three core pillars:
1. **AI Vision Anti-Spam:** Aggressive rejection of stock photos/retail renderings at upload.
2. **Automated Logistics:** Sub-category dimension mapping via Easyship/DPD API.
3. **AI Arbiter:** Multimodal LLM-based dispute resolution and automated Stripe refunds.

---

## 💳 Stripe Integration & Escrow Logic
This platform is built on **Stripe Connect** to ensure financial security and regulatory compliance.

* **Escrow Flow:** When an auction is won, the buyer pays the Final Bid + Automated Shipping Cost. Funds are held securely in escrow.
* **Verification:** All sellers undergo **Stripe Identity (KYC)** verification before payouts are enabled.
* **Automated Release:** Funds are auto-released to the seller 48 hours after a "Delivered" scan from the carrier.
* **Automated Dispute:** If a buyer disputes the condition, our **AI Arbiter** compares the delivery photos against the listing photos and triggers an instant "Refund" or "Release" via the Stripe API.

---

## 🛠 Technical Stack
* **Frontend:** React Native (Expo) - iOS & Android.
* **Backend:** Supabase (Auth, Postgres, Realtime WebSockets).
* **Logic:** Supabase Edge Functions (Deno) for Escrow and Scheduling.
* **AI Models:** GPT-4o / Claude 3.5 Sonnet (Vision & Arbitration).
* **Audio:** ElevenLabs (Hybrid AI Auctioneer).
* **Shipping:** Easyship & DPD API.

---

## 📂 Core Repository Structure
- `/src`: React Native application source code.
- `/supabase/functions`: Edge functions for Stripe webhooks and AI Arbitration.
- `/docs/legal`: 
    - [Terms of Service](terms.html) (Binding Bid Clauses)
    - [Privacy Policy](privacy.html) (Postcode Privacy)
    - [Refund Policy](shipping-refunds.html) (AI Arbiter Rules)

---

## ⚖️ Business Rules & Compliance
To maintain a high-trust environment, QuickClear strictly prohibits:
* **Immovable Goods:** No real estate or land.
* **Restricted Items:** No weapons, alcohol, tobacco, or live animals.
* **Direct Messaging:** To prevent off-platform "leakage" and fraud, there is zero user-to-user chat. All communication is handled by the AI Auctioneer.

---

## 🛠 Setup & Deployment
1. **Clone:** `git clone https://github.com/[YOUR_USERNAME]/quickclear.git`
2. **Install:** `npm install`
3. **Environment:** Configure `.env` with Stripe Secret Key, Supabase URL, and ElevenLabs API keys.
4. **Run:** `npx expo start`

---
© 2026 QuickClear Platform. Built for secure, automated commerce.
