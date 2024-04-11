# Lesson 8 Notes and Links

Notion site for session recording links on Youtube:
https://encodeclub.notion.site/aebb64ae7c7245f2a2cfd98da7dddfcf?v=328ebe0ce5754f2791eb8be1f19a9586

Instructor notes [they are detailed and have screenshots]:
 - [Instructor Notes](../instructor_slide_notes_and_homework/Lesson8.pdf)
 - [Homework](../instructor_slide_notes_and_homework/Homework8.pdf)


### Slido for class questions:
https://app.sli.do/event/9bhfXBfjYd6QpmY3g8tQLZ/live/questions



## Notes

 - Covered Authority v. Ownership
 - Upgrading programs
 - Program flow [entrypoint, processor, etc]
 - PDAs
 - Go over the homework todo


## Links

- Upgrading programs
  - https://jstarry.notion.site/Program-deploys-29780c48794c47308d5f138074dd9838
- SPL token code
  - https://github.com/solana-labs/solana-program-library/tree/master/token
- Solana Bootcamp - Episode 1 - Introduction to Solana [YouTube Playlist]
  - https://www.youtube.com/watch?v=0P8JeL3TURU&list=PLilwLeBwGuK6NsYMPP_BlVkeQgff0NwvU


## Homework

 - Create tokens
 - Create a program [example 1 and example 2]
  - Repo to play with: https://github.com/ExtropyIO/SolanaBootcamp/tree/main/examples_baremetal


### Setup to get going


From Discord:

_we need to downgrade Solana to 1.16.21 for the homework to work_


```
Regarding the second part of homework 8, for some architectures an error is produced when running npm run build
To prevent this, you need to use an older version of the solana-cli
That is run
sh -c "$(curl -sSfL https://release.solana.com/v1.16.21/install)"
rather than version 1.18.4
```
https://discord.com/channels/705799923014041651/1201884833434058772/1226218579419074714


```bash
jeremy@mac examples_baremetal % sh -c "$(curl -sSfL https://release.solana.com/v1.16.21/install)"
downloading v1.16.21 installer
  ✨ 1.16.21 initialized
```

Then run:

```
npm i
npm run build
```

Set the Solana config to local:

```
solana config set --url localhost
```

Check balance:

```solana balance
Error: Dynamic program error: No default signer found, run "solana-keygen new -o /Users/jeremy/.config/solana/id.json" to create a new one
```

DOH!

```
solana airdrop 100
Error: Dynamic program error: No default signer found, run "solana-keygen new -o /Users/jeremy/.config/solana/id.json" to create a new one
```

Setup a local wallet and remember to copy the word phrase to backup:

```
jeremy@mac examples_baremetal % solana-keygen new -o /Users/jeremy/.config/solana/id.json
Generating a new keypair
```

Free Money!!!1!

```
solana airdrop 100
Requesting airdrop of 100 SOL

Signature: 4U7UWATUbPoV2px5RGHHruVy7o2r46dD14r3UqQsdF1c3vh8QxegtrtSZAkW3NhRYzUtvdYVRpbrCXV2NzxzqfeW

100 SOL

```

Now check the balance:

```
solana balance
1000 SOL

```

You have infinite money glitch on your computer, may as well exploit it, eh?

Now try it:

```bash
cd ..
npm run deploy:1
npm run call:1
```

#### deployed example 1, Hooray!

```bash
Transaction executed in slot 1663:
  Signature: bw5EBwV6T7Y9hcBarAY5V4W3q8H2yoE7sy7YVQwdvWnstZ18Pu2EJPpaZF5BV4TX1DkjiaFCP5ZZVEDMekaY7Eo
  Status: Ok
  Log Messages:
    Program C6oSTBB3s2brGc1iZAysBKH1TrGuaEhsNgyskJ11pgGk invoke [1]
    Program log: [lib] Hello World Rust program entrypoint
    Program C6oSTBB3s2brGc1iZAysBKH1TrGuaEhsNgyskJ11pgGk consumed 141 of 200000 compute units
    Program C6oSTBB3s2brGc1iZAysBKH1TrGuaEhsNgyskJ11pgGk success
```

#### deployed example 2, Woot!

```bash
npm run deploy:2
npm run call:2
```

Well lokk at that, it worked!


```
Transaction executed in slot 3825:
  Signature: 4325vnSqHFgFxrPgmaSUwa5Dwf5f1iWZ9K8ZUnmpNsbq3kr3U8rLYfJsByMmbhKtLqNcJj4pZ2pbVt66DCaqf4ZJ
  Status: Ok
  Log Messages:
    Program Fn1ssxMhjJr8GqwJ1gLPA9mi7CJY1hdw2i82m6AgWxxA invoke [1]
    Program log: [lib] Solana Example2 counter program entrypoint
    Program log: [lib] hello account: 6MKHifRZdZJctEuC7ELqdtrCsenni63SnUfLFvMrp7u6
    Program log:  Greeted account has the correct program id
    Program log: Program added to the greeting counter struct stored at: 6MKHifRZdZJctEuC7ELqdtrCsenni63SnUfLFvMrp7u6
    Program log:  Greeted 1 time(s)!
    Program Fn1ssxMhjJr8GqwJ1gLPA9mi7CJY1hdw2i82m6AgWxxA consumed 24870 of 200000 compute units
    Program Fn1ssxMhjJr8GqwJ1gLPA9mi7CJY1hdw2i82m6AgWxxA success
```


## Other notes

Set the cluster to devnet:

```bash
solana config set --url https://api.devnet.solana.com
```


Set the keypair to my devnet keypair:

```
solana config set --keypair /Users/jeremy/devnet-solana-wallet/devnet-keypair.json
````

### Create a Token

Link:
https://chainstack.com/how-to-mint-solana-spl-tokens/


#### Steps:
 - Create Token
 - Create Account
 - Mint
 - Transfer


spl-token create-token

```bash
spl-token create-token
Creating token DVYMBZgJdXPXuyBwvtPpPfHUFRsfCp2j3RRFcNdwHFQp under program TokenkegQfeZyiNwAJbNbGKPFXCWuBvf9Ss623VQ5DA

Address:  DVYMBZgJdXPXuyBwvtPpPfHUFRsfCp2j3RRFcNdwHFQp
Decimals:  9

Signature: NH8ijEdt2nKE4RwksFuQiwNr5V2UpD6e3FWujiZ5151byhefzVEFEA9q7u23k8Q8ChktMSHLYGbYkdtvKVFkxFD
```

spl-token create-account DVYMBZgJdXPXuyBwvtPpPfHUFRsfCp2j3RRFcNdwHFQp

```
spl-token create-account DVYMBZgJdXPXuyBwvtPpPfHUFRsfCp2j3RRFcNdwHFQp
Creating account CkExZPqtpdzB1W4deDc6U5bxzsc1t91dkZ74CT955hRS

Signature: 39NmvHo59989TbsnAAHTkURNwkCE5jLARXRs1dVaCTWWCD1ruRTPCTwonUg1rpiS4JjYV4GN5tRZdAUcf4BBd2p2

```

spl-token mint DVYMBZgJdXPXuyBwvtPpPfHUFRsfCp2j3RRFcNdwHFQp 10000

```bash
spl-token mint DVYMBZgJdXPXuyBwvtPpPfHUFRsfCp2j3RRFcNdwHFQp 10000
Minting 10000 tokens
  Token: DVYMBZgJdXPXuyBwvtPpPfHUFRsfCp2j3RRFcNdwHFQp
  Recipient: CkExZPqtpdzB1W4deDc6U5bxzsc1t91dkZ74CT955hRS

Signature: 4bPPCeXiqZY2A9XZJY3wQ7ufdH74joqNEARLc6UBPMVy2Y9g5jZsuyaekuMqh3DzLvrNt4t9B6Z7fRkz2WSe1cic
```

On DevNet:
https://explorer.solana.com/address/DVYMBZgJdXPXuyBwvtPpPfHUFRsfCp2j3RRFcNdwHFQp?cluster=devnet


Token transfer:

```bash
spl-token transfer DVYMBZgJdXPXuyBwvtPpPfHUFRsfCp2j3RRFcNdwHFQp 100 24CFvjS6FE3LxZyKNVhGxXXV6N2zp2TWwP4eQ3ktV4XM
Transfer 100 tokens
  Sender: CkExZPqtpdzB1W4deDc6U5bxzsc1t91dkZ74CT955hRS
  Recipient: 24CFvjS6FE3LxZyKNVhGxXXV6N2zp2TWwP4eQ3ktV4XM
  Recipient associated token account: CkExZPqtpdzB1W4deDc6U5bxzsc1t91dkZ74CT955hRS

Signature: 5opu5h4izM8xUySHdNTx8Dwr2M6T9NWRDTqjrh5bqKTL3u5XCuQcnmaKArDJLssXsXM7gHVWLMrJdnhYFyQv8S8Z
```

TX:
https://explorer.solana.com/tx/5opu5h4izM8xUySHdNTx8Dwr2M6T9NWRDTqjrh5bqKTL3u5XCuQcnmaKArDJLssXsXM7gHVWLMrJdnhYFyQv8S8Z?cluster=devnet


My address has more tokens:

https://explorer.solana.com/address/24CFvjS6FE3LxZyKNVhGxXXV6N2zp2TWwP4eQ3ktV4XM/tokens?cluster=devnet


Send to `FUufJrZsAySQT5TBi3CK2DsZ7Ym2cmoUYPEUGMdQfHj9`

```bash
spl-token transfer --fund-recipient DVYMBZgJdXPXuyBwvtPpPfHUFRsfCp2j3RRFcNdwHFQp 1000 FUufJrZsAySQT5TBi3CK2DsZ7Ym2cmoUYPEUGMdQfHj9
Transfer 1000 tokens
  Sender: CkExZPqtpdzB1W4deDc6U5bxzsc1t91dkZ74CT955hRS
  Recipient: FUufJrZsAySQT5TBi3CK2DsZ7Ym2cmoUYPEUGMdQfHj9
  Recipient associated token account: 8U8JkdBKwfQ4LXFaAQdHwGe5djx3q78XzQYtg6iaHRtn
  Funding recipient: 8U8JkdBKwfQ4LXFaAQdHwGe5djx3q78XzQYtg6iaHRtn

Signature: KMfhhPt2TnKkq164rXQCtgoic2cbvWuVFSi4Exud3yaJ6iWAouRyPK28FEyiQmwkQUeZJ43v88kswBLpYURVoaT

```


### Create NFT

Link:
https://spl.solana.com/token



#### Steps:
 - Create Token
 - Create Account
 - Mint
 - Disable new minting
 - Transfer


spl-token create-token --decimals 0

```bash
spl-token create-token --decimals 0
Creating token DDJG3zMfyUeoBVhnSA48pHhnbnNpq41pAZswJ1eqXStQ under program TokenkegQfeZyiNwAJbNbGKPFXCWuBvf9Ss623VQ5DA

Address:  DDJG3zMfyUeoBVhnSA48pHhnbnNpq41pAZswJ1eqXStQ
Decimals:  0

Signature: 2ph7UetfUtb9jBUNzraLGaoVbhjxWXDUBvtK28gXQAdQizNdyaSCZzXAmH5878uCc4VWtzgbyH5KS2jpXKiiz4c
```

spl-token create-account DDJG3zMfyUeoBVhnSA48pHhnbnNpq41pAZswJ1eqXStQ

```bash
spl-token create-account DDJG3zMfyUeoBVhnSA48pHhnbnNpq41pAZswJ1eqXStQ
Creating account 5djTY2jCsuF8yvv3fnzASdwpAQTVSeu7T1ECC5HX2nbx

Signature: 4pUoZ8idNZnBHPxzJdtJGFwy9HoTEQYTGF9TSAuJUdqWTErHQqma4DCDNgEdkbszgP3WjWoqdnDJxxDNuWok8mqu
```

spl-token mint DDJG3zMfyUeoBVhnSA48pHhnbnNpq41pAZswJ1eqXStQ 1 5djTY2jCsuF8yvv3fnzASdwpAQTVSeu7T1ECC5HX2nbx

```bash
spl-token mint DDJG3zMfyUeoBVhnSA48pHhnbnNpq41pAZswJ1eqXStQ 1 5djTY2jCsuF8yvv3fnzASdwpAQTVSeu7T1ECC5HX2nbx
Minting 1 tokens
  Token: DDJG3zMfyUeoBVhnSA48pHhnbnNpq41pAZswJ1eqXStQ
  Recipient: 5djTY2jCsuF8yvv3fnzASdwpAQTVSeu7T1ECC5HX2nbx

Signature: 4wDnZdCaVv1RZz1ABBtmcAG6sENMPDVkWvY99x7VcVBPJfJnZ8PRPVEJqD2F4LmyxXhKUR6m3fRfbtYdYSHRrMB7
```


spl-token authorize DDJG3zMfyUeoBVhnSA48pHhnbnNpq41pAZswJ1eqXStQ mint --disable


```bash
spl-token authorize DDJG3zMfyUeoBVhnSA48pHhnbnNpq41pAZswJ1eqXStQ mint --disable
Updating DDJG3zMfyUeoBVhnSA48pHhnbnNpq41pAZswJ1eqXStQ
  Current mint: 24CFvjS6FE3LxZyKNVhGxXXV6N2zp2TWwP4eQ3ktV4XM
  New mint: disabled

Signature: 2iZnrwoEDuS7fnjoXQrVy4THuWobFCtfEmhsX2M1VRKXMH7xh2GcBXqkRe3hVbGbuEYRqMiopD3NjGfBriHtAXZw
```

spl-token account-info

```bash
spl-token account-info DDJG3zMfyUeoBVhnSA48pHhnbnNpq41pAZswJ1eqXStQ

SPL Token Account
  Address: 5djTY2jCsuF8yvv3fnzASdwpAQTVSeu7T1ECC5HX2nbx
  Program: TokenkegQfeZyiNwAJbNbGKPFXCWuBvf9Ss623VQ5DA
  Balance: 1
  Decimals: 0
  Mint: DDJG3zMfyUeoBVhnSA48pHhnbnNpq41pAZswJ1eqXStQ
  Owner: 24CFvjS6FE3LxZyKNVhGxXXV6N2zp2TWwP4eQ3ktV4XM
  State: Initialized
  Delegation: (not set)
  Close authority: (not set)
```

spl-token transfer

```bash
spl-token transfer DDJG3zMfyUeoBVhnSA48pHhnbnNpq41pAZswJ1eqXStQ 1 24CFvjS6FE3LxZyKNVhGxXXV6N2zp2TWwP4eQ3ktV4XM
Transfer 1 tokens
  Sender: 5djTY2jCsuF8yvv3fnzASdwpAQTVSeu7T1ECC5HX2nbx
  Recipient: 24CFvjS6FE3LxZyKNVhGxXXV6N2zp2TWwP4eQ3ktV4XM
  Recipient associated token account: 5djTY2jCsuF8yvv3fnzASdwpAQTVSeu7T1ECC5HX2nbx

Signature: BZCzmcKfqvtwXpM3hJ1aXPxnTTFLThyHhyab8nn6zfJsJB7BaXtfidF2WHFDsMYw8EUQhSZb9tqa2t3mVY52ise
```


spl-token account-info

```bash
spl-token account-info DDJG3zMfyUeoBVhnSA48pHhnbnNpq41pAZswJ1eqXStQ

SPL Token Account
  Address: 5djTY2jCsuF8yvv3fnzASdwpAQTVSeu7T1ECC5HX2nbx
  Program: TokenkegQfeZyiNwAJbNbGKPFXCWuBvf9Ss623VQ5DA
  Balance: 1
  Decimals: 0
  Mint: DDJG3zMfyUeoBVhnSA48pHhnbnNpq41pAZswJ1eqXStQ
  Owner: 24CFvjS6FE3LxZyKNVhGxXXV6N2zp2TWwP4eQ3ktV4XM
  State: Initialized
  Delegation: (not set)
  Close authority: (not set)
```


My account has more tokens:
https://explorer.solana.com/address/24CFvjS6FE3LxZyKNVhGxXXV6N2zp2TWwP4eQ3ktV4XM/tokens?cluster=devnet




