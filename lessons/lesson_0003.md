# Lesson 03



## Working with the Solana CLI

_Reference:_

https://docs.solanalabs.com/cli/examples/transfer-tokens

https://docs.solanalabs.com/cli/wallets/paper



```zsh
solana-keygen new --outfile ~/devnet-solana-wallet/devnet-keypair.json

cat devnet-keypair.json

solana-keygen pubkey devnet-keypair.json

solana-keygen verify 24CFvjS6FE3LxZyKNVhGxXXV6N2zp2TWwP4eQ3ktV4XM devnet-keypair.json

solana config set --url https://api.devnet.solana.com

solana config get

solana airdrop 1 24CFvjS6FE3LxZyKNVhGxXXV6N2zp2TWwP4eQ3ktV4XM --url https://api.devnet.solana.com
```

DOH!

```zsh
Error: airdrop request failed. This can happen when the rate limit is reached.
```

Try again with smaller amount works

```zsh
solana airdrop 0.1 24CFvjS6FE3LxZyKNVhGxXXV6N2zp2TWwP4eQ3ktV4XM --url https://api.devnet.solana.com
```

Success!!

```zsh
solana confirm -v 5886aP5RBK2Fxxhd9Fp2GuhPG298aXd1HpAg2V3GD3XgnphrNuuuvR3r8ogBZdWGQUdV6BvSt95K6XqKx15TY6uL

solana-keygen new --no-passphrase --no-outfile

solana transfer --from devnet-keypair.json 6rf4KrGYLvdz4DgMMkUAASKnEVJRJ3cEDa8fXUhjFW1m 0.1 --allow-unfunded-recipient --url https://api.devnet.solana.com --fee-payer devnet-keypair.json

solana confirm -v 2fbg2yJX2FPZaDzR5GoJyWBgFmfoBioceQoey7eh3wWBAPLYAkx73asPgPEUP1sZBX5RC96QBtFQXYpp4STXWMNL

solana balance 6rf4KrGYLvdz4DgMMkUAASKnEVJRJ3cEDa8fXUhjFW1m --url https://api.devnet.solana.com


solana-keygen recover -o devnet-keypair-02.json

solana transfer --from devnet-keypair-02.json 24CFvjS6FE3LxZyKNVhGxXXV6N2zp2TWwP4eQ3ktV4XM 0.099995 --allow-unfunded-recipient --url https://api.devnet.solana.com --fee-payer devnet-keypair-02.json

solana confirm -v 2mqHK7DgBDRVBRQHLgnqJMwBhsEXq8jm7h2bi4agBncfrsRHcdMLuFuDhT3FKtWddpP2SMqyiD3nPHD6WGqgtGnB

solana balance 6rf4KrGYLvdz4DgMMkUAASKnEVJRJ3cEDa8fXUhjFW1m --url https://api.devnet.solana.com
```

