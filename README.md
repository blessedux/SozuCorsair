# SozuMarket

**The permissionless P2P marketplace powering Sozu Wallet (Stellar)**

SozuMarket is a peer-to-peer marketplace platform that connects users in Argentina who want to trade digital pesos (AR$) or cash for USDC on the Stellar blockchain. Built with a focus on privacy and self-custody—no KYC required. SozuMarket is a non-custodial, non-intermediary platform that facilitates direct peer-to-peer connections only, designed to scale use for the SozuWallet.

---

## Purpose in Sozu Capital Ecosystem

SozuMarket serves as a **matching platform** for Sozu Wallet users, providing a decentralized way to:

- **Find Counterparties**: Connect buyers and sellers of USDC/AR$ pairs
- **View Offers**: Browse available trades with pricing and user reputation data
- **Maintain Self-Custody**: All blockchain transactions occur directly between users' Stellar wallets—SozuMarket never touches funds
- **Trade Without KYC**: Permissionless access for users who value privacy
- **Direct P2P Trading**: Users execute trades directly with each other using their own wallets

**Important**: SozuMarket is a pure matching and information platform. We do not escrow, hold, custody, settle, resolve disputes, or intermediate payments. All transactions occur directly between users' wallets on the Stellar network.

This marketplace facilitates connections for users in the Sozu Capital ecosystem, enabling peer-to-peer entry and exit from the Stellar-based financial infrastructure.

---

## 🛠 Technical Stack

### Frontend

- **Framework**: Next.js (PWA)
- **Styling**: Tailwind CSS + Shadcn UI
- **Type**: Progressive Web App (PWA) for mobile and desktop

### Backend

- **Database & Backend**: Supabase or Firebase
- **Authentication**: JWT-based session tokens
- **Real-time**: Supabase real-time subscriptions (or Firebase)

### Blockchain Integration

- **Network**: Stellar
- **Wallet Integration**: Sozu Wallet API
  - Public key management
  - Balance reading
  - Transaction signing
  - Deep linking for wallet interactions

### Infrastructure

- **Hosting**: Vercel/Netlify (PWA)
- **Backend Functions**: Supabase Functions
- **Domain**: `market.sozu.cash`
- **CI/CD**: GitHub Actions

---

## 📋 MVP Scope

### 1. **Authentication & Identity**

- Passkeys login (non-KYC)
- Wallet linking via message signing
- User profile management

### 2. **Marketplace Core**

- **Buy USDC Flow**
  - Input ARS$ amount
  - Fetch matching offers
  - Display seller stats (price, limits, reputation)
  - Connect buyer with seller for direct trade
- **Sell USDC Flow**
  - Input USDC amount
  - Create sell offers
  - Auto-match with best buyers
  - Trade notifications

### 3. **Trade Coordination**

- Trade state tracking: `CREATED → AWAITING_PAYMENT → PAYMENT_SENT → PAYMENT_CONFIRMED → COMPLETED`
- Support for `CANCELLED` states
- Wallet integration for viewing balances and initiating transactions
- Deep linking to Sozu Wallet for user-initiated transactions
- Trade status visibility for users

### 4. **Trade Status Updates**

- Buyer marks "Payment Sent" (user-reported status)
- Optional transfer proof upload (user-provided)
- Seller confirms receipt (user-reported status)
- Trade completion tracking (informational only)
- Cool-down timer display (2-5 minutes)
- User-reported mismatch flagging

### 5. **Reputation Layer**

- Post-trade ratings (user-submitted)
- Reputation scoring (community-driven):
  - +1 for successful trade
  - -3 for user-reported issues
- User-reported suspicious activity flags
- Display metrics:
  - Trade count
  - Average completion time
  - User-reported issue percentage
  - User-verified payment methods

### 6. **Notifications**

- Browser push notifications
- Email fallback
- Events: Match found, Trade status updates, Payment sent/confirmed, Trade completed

### 7. **PWA UI Screens**

- Home (Buy/Sell)
- Offers board
- Trade detail view
- Counterparty payment information display
- Counterparty chat (optional)
- Profile/reputation
- Transaction history

### 8. **Admin & Safety**

- Admin dashboard (Supabase UI)
- User-reported flagged trades visibility
- User-reported issue visibility
- Account moderation capabilities (for platform abuse only)
- Pattern tracking for informational purposes

---

## 🔐 Security & Privacy

- **No KYC**: Users can trade without identity verification
- **Self-Custody**: All funds remain in user-controlled Stellar wallets—SozuMarket never has access
- **Non-Custodial**: SozuMarket does not hold, escrow, custody, settle, or intermediate any funds
- **Reputation System**: Community-driven trust mechanism based on user-reported data
- **Direct P2P**: All transactions occur directly between users' wallets on Stellar
- **No Payment Intermediation**: SozuMarket does not process, hold, or intermediate any payments

---

## 📁 Project Structure

```
SozuCorsair/
├── README.md
├── todo.md
└── [Project files to be created]
```

---

## 🧪 Testing Requirements

- End-to-end AR$ → USDC buy flow (matching and connection)
- End-to-end USDC → AR$ sell flow (matching and connection)
- Wallet signing + deep links
- Trade cancellations
- Trade status update flows
- Stress testing (200+ concurrent trade connections)

---

## 📝 License

MIT

---

## 🔗 Related Projects

- **Sozu Wallet**: The Stellar wallet that SozuCorsair powers
- **Sozu Capital**: The broader ecosystem

---

## ⚖️ Legal Disclaimer

SozuMarket is a peer-to-peer matching platform that connects users for direct trades. SozuMarket does not:

- Escrow or hold funds
- Provide custody services
- Settle transactions
- Resolve disputes
- Intermediate payments
- Act as a money transmitter or payment processor

All transactions occur directly between users' wallets on the Stellar network. Users are solely responsible for their trades and interactions with counterparties.
