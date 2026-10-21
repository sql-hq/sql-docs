# Vaults, recovery and privacy

A connected Ethereum account and a private RAILGUN vault are different things. Connecting the same account does not restore a lost private wallet automatically. Preserve the private recovery material and an encrypted backup before sending funds.

Vault encryption derives a 32-byte key using PBKDF2-SHA256 with 210,000 iterations. The portable backup separately uses PBKDF2-SHA256 with 600,000 iterations and AES-256-GCM, with a fresh 16-byte salt and 12-byte IV. The backup password must contain at least ten characters. Decryption must authenticate the backup rather than silently replacing a failed recovery with a new wallet. Public receiving-address metadata in the backup is not the same as its encrypted recovery secret.

The application scopes vault state to the wallet owner and network. Account changes and disconnect must lock the private session and invalidate stale asynchronous callbacks. Browser-local state is not a cloud backup, and private recovery data should never be placed in issue reports, analytics, public files or source-control history.

Synchronization must complete before spending. A healthy RPC endpoint, recent indexer events or an empty wallet scan do not prove full funded-history recovery. The public evidence records actual encrypted-backup restoration and matching funded balances/history for controlled wallets; it does not distribute those wallets or their backups.

Network fees, public transaction hashes and unshield destinations are visible on Ethereum. A private payment does not make its public gas-paying wallet invisible. Return-to-origin is a public return to the SDK-derived original destination.

The initial source release retains legacy compatibility modules and cryptographic tooling. It does not claim a clean independent security audit or comprehensive real external-wallet browser acceptance. Report vulnerabilities privately to support@sql.cash.
