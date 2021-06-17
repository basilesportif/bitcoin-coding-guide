# Urbit Bitcoin Implementation

## division of labor
We currently do everything except signing.
Signing will be implemented soon.

## bitcoin-utils.hoon
Exposed through `bitcoin.hoon`
- Motivation
- bit/byt/blop
- hashing
- hexb
- compactSize

## bitcoin.hoon
- `sur` types
- address manipulation
- transaction encoding/decoding

## bip implementations
Exposed through `bitcoin.hoon`
- bip158 (blockfilters)
- bip173 (Bech32)
- bip174 (PSBTs)
