# calculate genesis

use '--g' & '--coinbase-sig' to calculate genesis

'--coinbase-sig' is required, because genesis block scriptsig must contain additional information 
```
./minerd -a sha256d -o http://127.0.0.1:8332/ -O cf:mymm --no-getwork --no-longpoll --no-stratum --coinbase-addr=1JNxEnQC3ofS8vaZqQXcRzV4KVveZAwAed --g --coinbase-sig="why so serious"
```
the genesis just looks like
```
====================    genesis    ====================
genesis hash: 00000000009f46506b3ad70976c8c87aac52df40f3cda5a880f96bfbcce8a7c9
preblockhash: 0000000000000000000000000000000000000000000000000000000000000000
merkleroot: ce449ac92860bbec4532111d5d6608f04a72dba350ce6623b79d8a459b4cb4e9
traget: 0000000000ffffffffffffffffffffffffffffffffffffffffffffffffffffff
version: 1
time: 1531964789
bits: 1d00ffff
nonce: 3941343488
====================    genesis    ====================
```

then set the genesis params in [chainparams.cpp](./chainparams.cpp#L26)
