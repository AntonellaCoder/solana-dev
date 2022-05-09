# Develop in solana

## Start Instance, tools and wallet.

Create a linux virtual machine in aws or similar and updated it.

```Sudo apt update && sudo apt upgrade```

Install solana tools.

```sh -c "$(curl -sSfL https://release.solana.com/v1.10.8/install)"```

Exit from bash to update the path in shell.

Check solana version.

```solana --version```

Generating a new wallet.

```solana-keygen new```

Save in a safe place your BIP39 passphrase to recover your wallet.

Check your balance:

```solana balance```

You cant send some amount from your phantom wallet using pubkey.

## Token Program

Reference: https://spl.solana.com/token

Install rust from rustup.rs

```curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh```

Close and open the terminal to update the path.

Install this to avoid failure while installing CLI.
Reference: https://github.community/t/error-cargo-install-spl-token-cli/233526/3

```sudo apt update```
```sudo apt install libudev-dev```
```sudo apt install libssl-dev pkg-config```
```sudo apt install build-essential```
Exit and re-enter bash to update paths.

Install CLI tool token program

```cargo install spl-token-cli```

Create TOKEN

```slp-token create-token```

Create an ACCOUNT for your TOKEN.

```slp-token create-account <your token created>```

Mint

```spl-token mint <your token> <quantity> <your account>

Check the amount minted

```spl-token accounts```

Send it to a wallet

spl-token transfer --fund-recipient --allow-unfunded-recipient <your token> <ammount> <wallet to found>



