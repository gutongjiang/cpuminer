# calculate genesis

use **--g** and **--coinbase-sig** to calculate genesis

**--coinbase-sig** is required, because genesis block scriptsig must contain additional information 
```
./minerd -a sha256d -o http://127.0.0.1:8332/ -O cf:mymm --no-getwork --no-longpoll --no-stratum --coinbase-addr=1JNxEnQC3ofS8vaZqQXcRzV4KVveZAwAed --g --coinbase-sig="why so serious"
```
the genesis just looks like
```
====================    genesis    ====================
genesis hash: 00000000009f46506b3ad70976c8c87aac52df40f3cda5a880f96bfbcce8a7c9
merkleroot: ce449ac92860bbec4532111d5d6608f04a72dba350ce6623b79d8a459b4cb4e9
traget: 0000000000ffffffffffffffffffffffffffffffffffffffffffffffffffffff
version: 1
time: 1531964789
bits: 1d00ffff
nonce: 3941343488
====================    genesis    ====================
```

then set the genesis params in BTC [chainparams.cpp](./chainparams_btc.cpp#L26) line 26,54,109,128,

set the genesis params in BCH [chainparams.cpp](./chainparams_bch.cpp#L38) line 38,73,151,223,239,340,437


example of BCH genesis:
```
====================    genesis    ====================
genesis hash: 000000000069f8f996b2de31cf5f401e8d71ced82e86a8a16c680e5a063a1910
merkleroot: ae006c8bb669b51981011588b8c469a4f44b66378ac5057703095714cc548104
traget: 0000000000ffffffffffffffffffffffffffffffffffffffffffffffffffffff
versionHex: 1
version: 1
time: 1536375900
bits: 1d00ffff
nonce: 4103071042
====================    genesis    ====================
```

txs:
01000000010000000000000000000000000000000000000000000000000000000000000000ffffffff1c001a77687920736f20736572696f75730b2f454233322f414431322fffffffff0100f2052a010000001976a914bea0fbcba8ad12b85f5f2a0fa5f8f129812d072688ac00000000

```
{
  "txid": "ae006c8bb669b51981011588b8c469a4f44b66378ac5057703095714cc548104",
  "size": 113,
  "version": 1,
  "locktime": 0,
  "vin": [
    {
      "coinbase": "001a77687920736f20736572696f75730b2f454233322f414431322f",
      "sequence": 4294967295
    }
  ],
  "vout": [
    {
      "value": 50.00000000,
      "n": 0,
      "scriptPubKey": {
        "asm": "OP_DUP OP_HASH160 bea0fbcba8ad12b85f5f2a0fa5f8f129812d0726 OP_EQUALVERIFY OP_CHECKSIG",
        "hex": "76a914bea0fbcba8ad12b85f5f2a0fa5f8f129812d072688ac",
        "reqSigs": 1,
        "type": "pubkeyhash",
        "addresses": [
          "bitcoincash:qzl2p77t4zk39wzltu4qlf0c7y5cztg8yc7m5cmhmf"
        ]
      }
    }
  ]
}
```
