A X [User](https://twitter.com/lingland09/) made a [post](https://twitter.com/lingland09/status/1700970363713167450) about possible 21877 sybil wallets on zkSync.

![image](https://github.com/Stakeridoo/Sybil/assets/84278683/fb5a0e7e-8b0f-46f2-99ad-db5bc9488bbb)

We made a query to get all the wallets who claimed the GEM token transfer from that [contract](https://explorer.zksync.io/address/0xdea197d9920a7472050013ad7e8de0733da81d5c#transfers)

```
SELECT
  "transaction_hash",
  "from_address",
  "to_address",
  CAST("value" AS double)/1e18 as "value",
  "block_time",
  "process_time"
FROM
  zksync_mainnet.erc20_evt_transfer
WHERE "from_address" = '0xdea197d9920a7472050013ad7e8de0733da81d5c'
and "value" > '0.1'
order by "block_time" desc
```
