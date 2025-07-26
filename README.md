# BlockPass

BlockPass is a decentralized event ticketing platform built on the Internet Computer Protocol (ICP). By minting each ticket as an on‑chain token and leveraging transparent smart contracts, BlockPass eliminates fraud, scalping, and hidden fees, ensuring every sale, transfer, and redemption is publicly auditable.

## Proposed Features

* **Tokenized Tickets**: Mint and manage tickets as on‑chain tokens.
* **Anti‑Scalping**: Smart‑contract rules enforce purchase limits and resale windows.
* **Transparent Ledger**: Every transaction is recorded on‑chain for full auditability.
* **Permissionless Transfers**: Secure, peer‑to‑peer ticket transfers without intermediaries.
* **Internet Identity**: Seamless login and per‑user ticket management via ICP’s Internet Identity.

## Architecture

BlockPass consists of two core components:

1. **Event Factory Canister**: Deploys and indexes individual Event canisters.
2. **Event Canister**: Manages ticket minting, transfers, and redemptions using Motoko stable memory.

The Next.js front‑end interacts with canisters using `@dfinity/agent` and `@dfinity/auth-client`, serving a responsive UI built with Tailwind CSS and DaisyUI.

## Prerequisites

* [Node.js](https://nodejs.org/) v16+
* [dfx SDK](https://internetcomputer.org/docs/current/references/cli-reference/dfx-cli)
* ICP Internet Identity (for authentication)

## Setup & Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/your-org/blockpass.git
   cd blockpass
   ```

2. **Start the local ICP sandbox**

   ```bash
   dfx start --clean
   ```

3. **Deploy canisters**

   ```bash
   dfx deploy
   ```

4. **Install front‑end dependencies**

   ```bash
   cd ui
   npm install
   ```

5. **Configure environment**
   Create a `.env.local` file in `ui/` with:

   ```env
   NEXT_PUBLIC_FACTORY_CANISTER_ID=<your_factory_canister_id>
   NEXT_PUBLIC_NETWORK=http://localhost:8000
   ```

6. **Run the front‑end**

   ```bash
   npm run dev
   ```

   Open [http://localhost:3000](http://localhost:3000) in your browser.

## Usage

* **Create Event**: As an admin, call `createEvent` via the UI to launch a new event.
* **Buy Ticket**: Navigate to an event page and mint a ticket on‑chain.
* **View My Tickets**: Log in with Internet Identity and see all owned tickets.
* **Transfer & Redeem**: Initiate on‑chain transfers or redeem tickets at entrance.

## Technologies

* **Frontend**: Next.js App Router, React, Tailwind CSS, DaisyUI
* **Blockchain**: ICP canisters in Motoko, `@dfinity/agent`, Internet Identity
* **Tools**: dfx CLI, Node.js

## License

This project is released under the CC0 v1.0 Universal license.
