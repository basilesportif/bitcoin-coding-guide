# Bitcoin Transactions

## basic transaction structure
[Reference Transaction 1](https://github.com/bitcoin/bips/blob/master/bip-0143.mediawiki#native-p2wpkh)
[Reference Transaction 2](https://en.bitcoin.it/wiki/Weight_units) (see end)

- nVersion (used for relative locktimes)
- inputs (full value is spent)
  Starts with `num-inputs` (compact size)
  * source TXID
  * source index
  * unlocking scriptSig (if applicable, otherwise `0x00`)
  * nSequence
- outputs
  Starts with `num-outputs` (compact size)
  * value, little endian
  * locking script
- nLocktime

### hash (transaction id)
Hash all the above fields, in order.

### transaction size calculation
- sats/vbyte
- vbyte calculation

## bitcoin script, quick version
- used to lock outputs
- example in recent tx
- [lightning example](https://github.com/lightningnetwork/lightning-rfc/blob/master/03-transactions.md#to_local-output)

### addresses and spending scripts
- not actually in transactions
- convenience for wallet users
- base58
  * P2PKH
  * P2SH
- bech32
  * specific parsing rules in Bitcoin
  * P2WPKH
  * P2WSH

### funder locking vs. spender locking
- timeouts
  * OP_CTLV
  * OP_CSV
  * autochecking of time
    * `nLocktime`: always
    * `nSequence`: if nVersion is 2 and some conditions met

## Transaction Signing
* SIGHASH
 - stored at the end of signature (see BIP 0143 for example)
* witness program location (after outputs)
* PSBTs
* wallet signing
* future: `ANYPREVOUT`/`NOINPUT`

## Segwit

### Motivation
- transaction malleability
  * "ECDSA signatures are inherently malleable[3]; a third party without access to the secret key can alter an existing valid signature for a given public key and message into another signature that is valid for the same key and message. " [BIP0340](https://github.com/bitcoin/bips/blob/master/bip-0340.mediawiki)
  * malleable txs make Lightning hard
- block size
  
### Legacy Fields vs Segwit Fields
- legacy: all fields in the first transaction section
- segwit:
  * marker
  * flag
  * witness program
  
### tx hashing in segwit
- omit segwit fields
- same as before for old input scriptSigs
- segwit inputs set scriptSig to `0x00`
- tx id is not malleable if all inputs are segwit

## spending hashed scripts
- P2SH/P2WSH
- mechanics
- extra cost to spender, not funder
  * advantage for Lightning--cheaper cooperative closes
- problems
  * large locking scripts
  * have to store script (this won't change)

## resources
- [BIP143: Segwit Signing](https://github.com/bitcoin/bips/blob/master/bip-0143.mediawiki)
- [BIP173: Bech32](https://github.com/bitcoin/bips/blob/master/bip-0173.mediawiki)
- [vBytes & TX Size Calculations](https://en.bitcoin.it/wiki/Weight_units) 
