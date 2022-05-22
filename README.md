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

Install CLI tool token program (ubuntu 20 lts, t2.micro, 1gb swap added)

```cargo install spl-token-cli```

Create TOKEN

```spl-token create-token```

Create an ACCOUNT for your TOKEN.

```spl-token create-account <your token created>```

Mint

```spl-token mint <your token> <quantity> <your account>```

Check the amount minted

```spl-token accounts```

Send it to a wallet

```spl-token transfer --fund-recipient --allow-unfunded-recipient <your token> <ammount> <wallet to found>```

## Token name & logo

Create .png logo image less than 200kb.

Upload the image to github and get the raw address.

FORK github solana token list from your github account.

Go to assets folder, add a new folder and name it with your <TOKEN> address.
  
Upload your .png logo. (less than 200 kb)

Go to src/tokens/solana.tokenlist.json
  
Add an adicional recor with your data in json file

Commit your changes
  
Go to github.com/solana-labs/token-list
  
Click Pull REQUESTS, then New pull Requests.
  
Click compare across forks, then click head repository.
  
Choose the project forked, then Create pull request.
  
Check if it is accepted (closed).

  
## Recover old wallet with seed phrase thru terminal.

```solana-keygen recover -o private-key.json ASK```

Move the file private-key.json and rename it: ~/.config/solana/id.json

Check ```solana balance```





