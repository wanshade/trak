# Trakteer Blockchain App PRD v1.0

## product overview

### document title/version
Trakteer Blockchain App PRD v1.0

### product summary
This project is a crowdfunding and tipping platform similar to Trakteer, but it uses blockchain payments via the Base network. Users (fans) can send tips or support to creators directly on-chain, and creators can withdraw their funds to their crypto wallets. The tool will focus on fast, low-fee transactions, transparent funding, and easy onboarding for non-crypto native users.

## goals

### business goals
- Enable creators to monetize content directly on-chain with minimal fees
- Attract creators and users interested in Web3 payments and transparency
- Build the MVP to validate user interest in crypto-native tipping in Indonesia

### user goals
- Fans can tip creators easily with Base network tokens
- Creators can claim tips to their wallets securely
- Both parties can track transaction history transparently

### non-goals
- Does not aim to support fiat payments in MVP
- Does not handle tax reporting or compliance automation in MVP
- No multi-chain support in initial release (Base only)

## user personas

### key user types
- Creator (content creators, artists, educators)
- Fan (supporter, student, follower)

### basic persona details

#### creator
- Age 18-35, digital native
- Seeks direct monetization channel
- Comfortable with or learning Web3 basics
- Needs easy withdrawal process

#### fan
- Age 18-35, digital native
- Wants to support favorite creators with small tips (e.g. 0.001 ETH)
- May have limited Web3 experience

### role-based access
- Creator: manage profile, view tips received, withdraw
- Fan: view creator profiles, send tips

## functional requirements

| ID | Requirement | Priority |
|----|-------------|----------|
| FR-001 | Fan can connect wallet (Base supported wallets) | High |
| FR-002 | Fan can view creator profiles with tip options | High |
| FR-003 | Fan can send tip in Base network token | High |
| FR-004 | Creator can connect wallet to receive tips | High |
| FR-005 | Creator dashboard shows tips received with tx hash | High |
| FR-006 | Creator can withdraw tips anytime to wallet | High |
| FR-007 | Home page shows list of creators with search | Medium |
| FR-008 | Fans can leave public messages with their tips | Medium |
| FR-009 | Authentication via wallet signature | High |
| FR-010 | Responsive UI for mobile and desktop | High |

## user experience

### entry points
- Fans: landing page with creator list
- Creators: landing page CTA to onboard as creator

### core experience
- Connect wallet
- View creator profile
- Enter tip amount and send tip on-chain
- Confirmation with tx hash
- For creators: dashboard with list of received tips

### advanced features
- Public message/comments on tips
- Creator profile customization

### UI/UX highlights
- Web3 onboarding flow (connect wallet, network switch to Base)
- Simple, familiar tipping UI similar to Trakteer or Ko-fi
- Transaction status notifications

## narrative

As a fan, I want to support my favorite creator by sending tips using my crypto wallet on Base network, so that I can contribute directly with low fees and see the transaction instantly confirmed on-chain. As a creator, I want to receive tips easily in my wallet and track who sent them and how much, so I can focus on creating content without worrying about platform payout delays.

## success metrics

### user-centric
- Number of successful tips per creator per month
- Time taken for fans to complete tipping flow

### business
- Number of active creators onboarded
- Total tip volume processed (in Base tokens)

### technical
- 99.9% uptime
- <2s average page load time
- Transaction success rate >95%

## technical considerations

### integration points
- Base network RPC and smart contract for tipping
- Wallet providers (e.g. MetaMask, Coinbase Wallet)

### data storage/privacy
- Minimal user data storage (no passwords)
- Store creator metadata and messages in backend database (e.g. Supabase or MongoDB)
- Transactions and balances on-chain (Base)

### scalability/performance
- Scale reads with indexed DB for creator profiles
- Writes (tips) are on-chain, scale with Base network

### potential challenges
- User education on network switching to Base
- Gas fee volatility
- Smart contract security and audit requirements

## milestones & sequencing

### project estimate
- 6-8 weeks for MVP

### team size
- 1 PM
- 1 smart contract/blockchain engineer
- 1 backend engineer
- 1 frontend engineer
- 1 UI/UX designer

### suggested phases
1. Requirements & design (week 1)
2. Smart contract development & testnet deployment (week 2-3)
3. Frontend wallet integration & tipping UI (week 3-4)
4. Backend dashboard & creator management (week 4-5)
5. QA, bug fixing, testnet end-to-end (week 6)
6. Mainnet launch & user onboarding (week 7-8)

## user stories

### US-001 – Connect wallet (Fan/Creator)
**Description:** As a user, I want to connect my wallet so I can use the platform features.  
**Acceptance criteria:**  
- User can connect supported wallet  
- User sees connection success confirmation  
- If wallet is not on Base, user is prompted to switch

### US-002 – View creator profile
**Description:** As a fan, I want to view a creator's profile to learn about them before tipping.  
**Acceptance criteria:**  
- Fan can see creator name, bio, profile picture  
- Fan can see tip options

### US-003 – Send tip
**Description:** As a fan, I want to send a tip in Base token to a creator.  
**Acceptance criteria:**  
- Fan can enter amount  
- Fan confirms transaction in wallet  
- Successful tx updates creator dashboard

### US-004 – View tip confirmation
**Description:** As a fan, I want to see confirmation and tx hash after sending tip.  
**Acceptance criteria:**  
- UI displays success state with tx hash link to explorer

### US-005 – Creator onboarding
**Description:** As a creator, I want to connect my wallet and create a profile to start receiving tips.  
**Acceptance criteria:**  
- Creator connects wallet  
- Creator fills out name, bio, profile picture  
- Profile is saved and visible to fans

### US-006 – Creator dashboard
**Description:** As a creator, I want to see tips received with details.  
**Acceptance criteria:**  
- Dashboard shows list of tips with amount, sender address, message (if any), tx hash

### US-007 – Withdraw tips
**Description:** As a creator, I want to withdraw my tips to my wallet.  
**Acceptance criteria:**  
- Withdraw button sends available balance to creator wallet  
- Successful withdrawal shows confirmation

### US-008 – Post message with tip
**Description:** As a fan, I want to leave a public message with my tip.  
**Acceptance criteria:**  
- Fan can enter text message  
- Message is displayed on creator dashboard

### US-009 – Authentication via wallet signature
**Description:** As a user, I want to authenticate securely without creating passwords.  
**Acceptance criteria:**  
- System uses wallet signature for authentication  
- Session persists until user disconnects

### US-010 – View all creators
**Description:** As a fan, I want to browse and search all available creators.  
**Acceptance criteria:**  
- Home page shows list of creators  
- Search bar filters creators by name
