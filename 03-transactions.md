# Bitcoin Transactions

## basic transaction structure
[Reference Transaction](https://github.com/bitcoin/bips/blob/master/bip-0143.mediawiki#native-p2wpkh)

- nVersion (used for relative locktimes)
- inputs (full value is spent)
  Starts with `num-inputs` (compact size)
  * source TXID
  * source index
  * signature (if applicable)
  * sequence
- outputs
  Starts with `num-outputs` (compact size)
  * value, little endian
  * locking script
- nLocktime

## bitcoin script, quick version
- used to lock outputs
- example in recent tx
- [lightning example](https://github.com/lightningnetwork/lightning-rfc/blob/master/03-transactions.md#to_local-output)

### addresses
- not actually in transactions
- convenience for wallet users
- base58
  * P2PKH
  * P2SH
- bech32
  * P2WPKH
  * P2WSH




## Segwit Changes
