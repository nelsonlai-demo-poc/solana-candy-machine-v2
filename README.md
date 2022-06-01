# candy-machine-v2

## Clone & Install Metaplex

### clone:

```sh
git clone https://github.com/metaplex-foundation/metaplex.git ~/metaplex
```

### install:

```sh
yarn install --cwd ~/metaplex/js/
```

### check version:

```sh
ts-node ~/metaplex/js/packages/cli/src/candy-machine-v2-cli.ts --version
```

## Solana

### install:

```sh
sh -c "$(curl -sSfL https://release.solana.com/v1.10.20/install)"
```

### create wallet keypair:

```sh
solana config set --keypair ~/.config/solana/devnet.json
```

### setup environment:

set dev wallet:

```sh
solana config set --keypair ~/.config/solana/devnet.json
```

set dev environment:

```sh
solana config set --url https://metaplex.devnet.rpcpool.com/
```

check config:

```sh
solana config get
```

### airdrop

```sh
solana airdrop 2
```

## Candy Machine

### create candy machine:

```sh
ts-node ~/metaplex/js/packages/cli/src/candy-machine-v2-cli.ts upload \
    -e devnet \
    -k ~/.config/solana/devnet.json \
    -cp config.json \
    -c example \
    ./assets
```

### verify upload

```sh
ts-node ~/metaplex/js/packages/cli/src/candy-machine-v2-cli.ts verify_upload \
    -e devnet \
    -k ~/.config/solana/devnet.json \
    -c example
```

### update candy machine:

```sh
ts-node ~/metaplex/js/packages/cli/src/candy-machine-v2-cli.ts update_candy_machine \
    -e devnet \
    -k ~/.config/solana/devnet.json \
    -cp config.json \
    -c example
```

### mint one token:

mint:

```sh
ts-node ~/metaplex/js/packages/cli/src/candy-machine-v2-cli.ts mint_one_token \
    -e devnet \
    -k ~/.config/solana/devnet.json \
    -c example
```

check:

```sh
spl-token accounts
```

## Whitelist SPL Token

### create:

```sh
spl-token create-token
```

### check supply:

```sh
spl-token supply <your-token-address>
```

### create account for the token

```sh
spl-token create-account <your-token-address>
```

### mint token

```sh
spl-token mint <your-token-address> <amount>
```

### check accounts

```sh
spl-token accounts
```

### transfer token

```sh
spl-token transfer <your-token-address> <amount> <target-address>
```
