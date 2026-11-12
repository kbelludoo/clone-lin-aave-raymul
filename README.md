# clone-lin-aave-raymul

Experimental i64-positive LIN clone of Aave V3 `WadRayMath.rayMul` / `rayDiv`
(RAY'=1e9, 128-bit half-up). **Not** mainnet uint256 / RAY=1e27.

**Proofs live in [kbelludoo/lin-open](https://github.com/kbelludoo/lin-open)** (`examples/aave_raymul/`, `make aave-raymul-proof`).
This repository is the LIN copy only.

- Kernel: `src/lin_aave_raymul.lin`
- Upstream pin (hash-only, Solidity **not** vendored): `aave/aave-v3-core` `782f51917056a53a2c228701058a6c3fb233684a` path `contracts/protocol/libraries/math/WadRayMath.sol` sha256 `fae5b995ec613cc213050c99ea6352c9c18ceebba106d03b1726cfa8f1f0124e` git blob `f61fe87f2f2748144cd4d113c848e649c41a4e5d` (MIT after BUSL Change Date 2023-01-27).
- Named goldens: `rayMul(1, 5e8) → 1` vs floor `0`; `rayDiv(2, 3) → 666666667` vs floor `666666666`; `rayMul(1e10, 1e10) → 1e11` vs naive i64 wrap `7766279631452241920`.

Not claimed: aToken / pool parity, TVL savings, replacing Aave or the EVM, zk soundness, `wadMul`/`rayToWad` (separate clone-lin repos).
