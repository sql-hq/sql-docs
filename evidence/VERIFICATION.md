# How to verify this evidence

## On-chain evidence

Open the seven Ethereum mainnet transaction links in ANNOUNCEMENT.md. Check that each transaction succeeded on chain ID 1.

The receipt summary also records the block number/hash, UTC block timestamp, confirmation count when collected, gas used, effective gas price and actual network fee. Its canonical block hash is checked against the receipt. The fee is calculated as:

```text
actual network fee in wei = gasUsed × effectiveGasPrice
```

For the normal withdrawal and return-to-origin, USDC Transfer logs are independently checked for credits of 9,776 and 9,951 units respectively to the submitting test wallet. USDC uses six decimal places. Private wallet addresses and owner addresses are intentionally omitted from this downloadable summary; the underlying public transactions remain visible on Ethereum.

RAILGUN transaction input data is available through the explorer links or an Ethereum RPC's eth_getTransactionByHash method. Successful execution of proof-requiring RAILGUN operations is on-chain evidence of contract acceptance. This package does not contain private witnesses, proving secrets, spending keys or recovery phrases. Approvals and shields must not be mislabeled as zero-knowledge proof verifications.

## Off-chain recovery evidence

operator-test-results.json records the actual successful acceptance-runner results:

- Normal shield → private payment → normal withdrawal → encrypted-backup recovery.
- Separate shield → return-to-origin → preservation of the earlier private balance → encrypted-backup recovery.

The normal cycle checked both vaults' recovered balances against their pre-recovery balances and required at least two history entries per vault. The origin-return cycle recovered the recipient vault again, checked its final balance, and required at least four history entries.

These are operator-reported SDK assertions, **not independently signed third-party attestations**. An Ethereum receipt cannot by itself prove that an off-chain backup was restored. The record identifies this distinction explicitly.

operator-unit-tests.txt is the filtered recorded output of the successful 19-test operator unit suite. It is not a claim that a new browser test, independent security audit or external-wallet acceptance pass was performed.

## File integrity

On a system with sha256sum, extract the ZIP, open that directory and run:

```text
sha256sum -c SHA256SUMS.txt
```

Checksums establish file integrity against the supplied manifest, not author identity or independent certification. Receipt observations may gain more confirmations after the recorded collection time.
