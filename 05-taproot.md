# taproot

## motivation
- more privacy for cooperative closes
- more fee-efficient spending of complex scripts
- integrate Schnorr signatures
- additional functionality (e.g. PTLCs)

## detailed summary
[Based on this](https://bitcoinops.org/en/newsletters/2019/05/14/#overview-of-the-taproot--tapscript-proposed-bips)
- aggregate pubkey
- key tweaking w script Merkle root
- spending a Merkle path

### MuSig
- hostile pubkey choice problem
- solution: force pubkeys to commit to all others

### Adaptor Signatures
- intuition: `R` commits to more information than just `k`
- use: prove you got secret in a signature

## timeline
- miners signaled activation recently (June 2021)
- nodes are expected to be able to use from November 2021

## resources
- [Bitcoin Ops Guide](https://bitcoinops.org/en/newsletters/2019/05/14/#overview-of-the-taproot--tapscript-proposed-bips))
- [PTLCs/Payment Points](https://suredbits.com/payment-points-part-1/) 

### schnorr/MuSig/adapter signatures
- [Tad Dryja Talk (1st half good for Schnorr)](https://www.youtube.com/watch?v=palE3z-uglQ)
- [Rene Pickhardt Walkthroughs](https://www.youtube.com/playlist?list=PLaRKlIqjjguCILECVRXqVhec6yaNYyeMT)
- [Andrew Poelstra Talk](https://www.youtube.com/watch?v=j9Wvz7zI_Ac)
- [Schnorr MuSig Paper](https://eprint.iacr.org/2018/068.pdf)
- [BIP340: Schnorr Signatures](https://github.com/bitcoin/bips/blob/master/bip-0340.mediawiki)
- [BIP341: Segwit v1 (Taproot) Spending Rules](https://github.com/bitcoin/bips/blob/master/bip-0341.mediawiki) 
- [BIP342: Validation of Taproot Scripts](https://github.com/bitcoin/bips/blob/master/bip-0342.mediawiki)
