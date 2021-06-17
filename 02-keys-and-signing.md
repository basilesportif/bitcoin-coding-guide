# Keys and Signing

## Elliptic Curve Basics
### Basic Operations & Properties
- add
  * point to itself
- multiply
- distributive property
  * c = a+b
  * (a+b)G = aG + bG = cG
  * allows you to "reach" cG in log time

### Signing
- hash message
- Hoon code example

### En/Decrypting
* choosing a symmetric key seed
  - each must know other's pubkey
  - "meet me at a point, only we 2 can find it"
* use symmetric key to encrypt

### Schnorr
- implemented in upcoming Taproot upgrade
- wasn't used by Satoshi due to patent issues (patent expired 2008) 
- signature malleability
- algorithm simplicity
- see [BIP340](https://github.com/bitcoin/bips/blob/master/bip-0340.mediawiki)

## BIP32 and Key Derivation
* [Tool to Try Examples](https://iancoleman.io/bip39/)
* how mnemonics work
* passphrases
* xpubs

## Resources
* https://hackernoon.com/what-is-the-math-behind-elliptic-curve-cryptography-f61b25253da3
