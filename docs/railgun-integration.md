# RAILGUN integration

## Active Ethereum mainnet configuration

| Setting | Value |
| --- | --- |
| Chain ID | 1 |
| RAILGUN proxy | 0xfa7093cdd9ee6932b4eb2c9e1cde7ce00b1fa4b9 |
| Relay adapter | 0xac9f360ae85469b27aeddeafc579ef2d052ad405 |
| USDC | 0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48 |
| USDC decimals | 6 |
| Deployment block | 14737691 |
| ENS text key | railgun |

The adapter uses the official wallet, engine and shared-model packages pinned in its manifest. The current transaction-ID configuration is V2 Poseidon Merkle. SQL does not replace the RAILGUN verifier or claim ownership of those upstream contracts.

## Financial flows

1. **Shield:** approve the canonical USDC token for the actual RAILGUN spender, generate the SDK deposit payload, submit from the connected wallet and confirm the receipt. A mined shield is not necessarily normally spendable immediately.
2. **Private payment:** resolve and validate receiving 0zk addresses, synchronize actual notes and proof status, require sufficient spendable funds, construct the proof and submit the transaction. SQL supports up to ten recipients per transfer; the published real-money test used one controlled recipient.
3. **Normal unshield:** synchronize the private wallet, review the public destination and amount, generate the SDK proof and submit through the user's wallet. The public token transfer and network fee are visible on Ethereum.
4. **Return-to-origin:** inspect the original shield through the official SDK, obtain the original destination and returnable amount, then prove and submit that specific escape path. It is not an arbitrary-recipient withdrawal or a way to return already-spent shield outputs.

PPOI validation is distinct from transaction mining and from gas availability. Increasing gas does not make a PPOI-pending note normally spendable. The origin-return path does not fabricate PPOI clearance.

## Evidence and limits

See [the seven confirmed transactions](../evidence/ANNOUNCEMENT.md). Normal withdrawal credited 0.009776 USDC. The separate origin return credited 0.009951 USDC. Both funded-backup recovery checks passed in the operator runner. Those assertions are distinguished from public receipt evidence.

The $SQL project-token contract, 0x5081b481aa5F27050588Eab2F10d88fF45302afE, is displayed for information. It is not the supported private asset, the deposit destination or a replacement for USDC.

[SDK source](https://github.com/sql-hq/railgun-sdk/tree/main/src) · [Application integration](https://github.com/sql-hq/sql-cash/tree/main/apps/web/src) · support@sql.cash
