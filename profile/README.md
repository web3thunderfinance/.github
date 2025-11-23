# Thunder Finance

Thunder Finance is a mixer that incentivizes Privacy paying yields.

## Details

An EVM-compatible privacy-focused mixer that deploys pooled legit deposits into external lending markets (e.g. Aave) to earn real yield.
After KYC, users deposit supported ERC20 stablecoins through commitment-based privacy, accrue yield while funds are pooled, and later withdraw
principal + proportional yield using a secret (commitment/nullifier) flow. The destination wallet is also KYC'd. Fully compliant with OFAC and other AML regulations.

## How is it made

Web3 Thunder Finance is built as an EVM-compatible yield mixer using Solidity 0.8.19 and the Foundry development framework. The core architecture revolves around Web3ThunderFinanceMixer.sol, which pools user deposits and routes them into Aave V3 markets to generate real yield while preserving privacy via a commitment/nullifier scheme.

We leverage Aave V3 as our primary yield source, allowing us to transform idle pooled assets into productive capital without managing complex lending logic ourselves. The project is deployed on the Celo Blockchain (Mainnet & Alfajores), chosen for its fast block times and negligible gas fees, which are critical for a privacy protocol that requires frequent user interactions. We also utilize OpenZeppelin libraries for robust security (AccessControl, ReentrancyGuard) and CeloScan for contract verification via custom Foundry configurations.

A notable "hacky" detail is our current yield accounting: instead of minting internal share tokens, we simply track totalPrincipal and calculate yield dynamically by reading the contract's rebasing aToken balance (yield = aTokenBalance - totalPrincipal). Additionally, the privacy mechanism is currently a prototype—it uses a raw commitment map without

ZK proofs and Merkle trees using Circom, effectively, "stubbing" the heavy cryptography to focus on the yield integration first.

## Grants and Equity

We are looking for grants/investments to continue working on the project. 

Telegram: @jeffprestes

