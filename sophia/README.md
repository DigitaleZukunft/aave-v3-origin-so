# Aave on Aeternity (Sophia) - Draft Plan

This folder contains initial scaffolding and notes to port core Aave V3 concepts to Aeternity's Sophia smart contracts.

Scope (MVP):
- Core pool-like contract exposing supply/withdraw/borrow/repay primitives
- Token accounting using Sophia state (no ERC-20); optional AE Fungible Tokens bridge later
- Interest accrual simplified (linear index) to validate UI integration

Contracts:
- Pool.aes: entrypoint module with user actions
- Tokens.aes: basic balance and share accounting for aToken/vToken
- Math.aes: shared math helpers

UI integration:
- Set NEXT_PUBLIC_USE_AETERNITY=true and NEXT_PUBLIC_AE_NODE_URL to point the interface at the Aeternity node
- The UI will send raw TX via the AeternityAdapter shim

Limitations:
- Full parity with Solidity is not included in this draft
- Permit signatures, EIP-712, and multicall are not supported in AE mode yet