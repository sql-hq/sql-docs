# Architecture

SQL Cash is a self-custody private-USDC interface on Ethereum mainnet. Reown connects the user's Ethereum wallet; the RAILGUN SDK manages the private wallet, encrypted notes, proof generation and history.

The browser owns the private vault. The connected wallet approves and submits public Ethereum transactions. A restricted server-side RPC gateway forwards permitted read requests to a configured provider without exposing its credential. It is not a signing endpoint, custody service or server-side recovery mechanism.

The application source includes retained legacy SQL/NULL compatibility modules and Solidity source. Their historical network is Sepolia. The active mainnet financial system is RAILGUN, not a newly deployed SQL/NULL pool. Do not treat historical verifier or mock-token addresses as mainnet payment targets.

## Repositories

[Application](https://github.com/sql-hq/sql-cash) contains the UI and gateway. [SDK](https://github.com/sql-hq/railgun-sdk) contains the reusable integration. [Public evidence](../evidence/ANNOUNCEMENT.md) records the controlled mainnet tests and their scope.

## Deployment

Configure your own Reown project and allowed origins. Store a paid RPC URL only in a server-side environment variable. Build the frontend, then serve dist with the included gateway. Browser-visible configuration contains no signing key. The example configuration disables mainnet submission until the operator explicitly enables it.

Support: support@sql.cash.
