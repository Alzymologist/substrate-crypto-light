This is largely based on
[`sp_core`](https://docs.rs/sp-core/latest/sp_core/) crate. Draft.

Key differences here:

- no-std compatible with arm,
- sr25519 supports external Rng, for usability on baremetal
- ecdsa support based on pure Rust crate `k256` (TODO need to transfer stuff
  here from Kampela code, as of now), to avoid compiling difficulties
  (original `sp-core` has ecdsa from `secp256k1` C wrapper crate and it does
  not compile on certain no-std targets and creates extremely large binary
  blob on others)
