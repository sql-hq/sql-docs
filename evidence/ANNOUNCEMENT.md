# SQL Cash — Mainnet Financial Tests Passed

SQL Cash has completed its controlled real-funds tests on Ethereum mainnet.

**All tested financial flows passed:**

- USDC deposit into RAILGUN.
- Private USDC payment between test vaults.
- Normal withdrawal to the test wallet.
- Return of a separate pending deposit to its original wallet.
- Encrypted-backup recovery with matching funded balances and transaction history.

**7 successful on-chain transactions · 0.02 USDC deposited · 0.001391102994798993 ETH in actual network fees.**

The normal withdrawal credited **0.009776 USDC**. The separate return-to-origin credited **0.009951 USDC** and preserved the pre-existing private balance. These are small-value acceptance tests, not a claim that the entire deposited amount was withdrawn.

## Public transaction evidence

| Test transaction | Result | Ethereum mainnet receipt |
| --- | --- | --- |
| USDC approval — normal cycle | PASS | [0x8800e177eb1a84ca3a756d6fa1c8d435ba8761459023ebdc41092fb456d00063](https://etherscan.io/tx/0x8800e177eb1a84ca3a756d6fa1c8d435ba8761459023ebdc41092fb456d00063) |
| USDC shield — normal cycle | PASS | [0x448241176ae2b8f927dd6c84becefccae110a43acf012f545873e37df1c5f3d1](https://etherscan.io/tx/0x448241176ae2b8f927dd6c84becefccae110a43acf012f545873e37df1c5f3d1) |
| Private payment | PASS | [0xa6c04d697e93880b578add23da7b8d4a67227ba4ebda130a4d4d202a87bb588f](https://etherscan.io/tx/0xa6c04d697e93880b578add23da7b8d4a67227ba4ebda130a4d4d202a87bb588f) |
| Normal withdrawal | PASS | [0x89c960b56254a0c50027efcce54721d9b4b7efc6f6b9624600de617f42202dbc](https://etherscan.io/tx/0x89c960b56254a0c50027efcce54721d9b4b7efc6f6b9624600de617f42202dbc) |
| USDC approval — origin-return cycle | PASS | [0xa641ebde564aeb15cdf804cc50effbb197236557a884d31c0dc4f0b0f105186b](https://etherscan.io/tx/0xa641ebde564aeb15cdf804cc50effbb197236557a884d31c0dc4f0b0f105186b) |
| Separate USDC shield | PASS | [0x45a63d20519cde49ecf04e233bd0b95cbd2ebbeec63057257ae089f0344dde69](https://etherscan.io/tx/0x45a63d20519cde49ecf04e233bd0b95cbd2ebbeec63057257ae089f0344dde69) |
| Return to original wallet | PASS | [0x8060c2e37ee7424e6bdac80e4f9821c3a63e9f1c9670a6f3125cc9af355f292c](https://etherscan.io/tx/0x8060c2e37ee7424e6bdac80e4f9821c3a63e9f1c9670a6f3125cc9af355f292c) |

## What is attached

The evidence package contains independently re-queried public transaction receipt summaries, the operator's successful funded-recovery results, the recorded 19-test operator unit-suite summary, verification instructions and SHA-256 file checksums.

**Scope:** “All passed” refers to the financial flows listed above. This announcement is not an independent security audit, a claim that every public-release check passed, or certification of real external-wallet browser acceptance. Public on-chain receipts and operator-reported recovery assertions are identified separately in the evidence.

GitHub: https://github.com/sql-hq  
X: https://x.com/SQL_Cash
