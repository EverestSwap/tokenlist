# Everest Exchange Token List

Token Lists is a specification for lists of token metadata (e.g. address, decimals, etc.) that can be used by any dApp
interfaces that needs one or more lists of tokens. Anyone can create and maintain a token list, as long as they follow
the specification. The Everest community invites you to add your token to our tokenlists!


## Adding Your Token to an Existing List


### General Requirements
1. Token contract should be verified on the explorer.
2. Token must be added to a list that it qualifies for:
    * **[Mainnet Tokenlist](./lists/mainnet.tokenlist.json)**: Token must be on the ICE Mainnet network.
    * **[Arctic Testnet Tokenlist](./lists/testnet.tokenlist.json)**: Token must be on the Arctic Testnet network.


## Adding Your Token
1. Add an entry in the `tokens` field of the appropriate tokenlist. Please use the [checksum address](https://docs.ethers.io/v5/api/utils/address/#address). Here is an example using EVRS:
    ```json
    {
      "chainId": 550,
      "address": "0x9F9F2Ac260F6332113795e15A6F75Fa628A15E7f",
      "decimals": 18,
      "name": "Everest",
      "symbol": "EVRS",
      "logoURI": "https://raw.githubusercontent.com/everestswap/tokenlist/main/assets/0x9F9F2Ac260F6332113795e15A6F75Fa628A15E7f/logo.png"
    }
    ```
2. Update the `timestamp` field to the current timestamp.
3. Update the `version` field to adhere to semantic versioning:

    * Increment major version when tokens are removed
    * Increment minor version when tokens are added
    * Increment patch version when tokens already on the list have minor details changed (name, symbol, logo URL, decimals)

    ***Note:*** Changing a token address or chain ID is considered both a remove and an add, and should be a major version update.

## Adding Your Token Logo

Token logos are [hosted here](./assets).

1. Create a new directory named using your [checksum token address](https://web3js.readthedocs.io/en/v1.7.1/web3-utils.html#tochecksumaddress).
2. Add your 24x24 token image as a file named `logo_24.png` inside the directory.
3. Add your 48x48 token image as a file named `logo_48.png` inside the directory.
4. No image should be larger than 10 KB.
5. Token should be verified on an explorer.
6. Create a PR titled `Add [TOKEN_NAME]` to the `main` branch.


## Example directory structures
```
├─ tokens/
│
└─┬─ assets/
  │
  ├─┬─ 0x60781C2586D68229fde47564546784ab3fACA982/
  │ ├── logo_24.png
  │ ├── logo_48.png
  │ └── logo.png
  │
  ├─┬─ 0xB31f66AA3C1e785363F0875A1B74E27b85FD66c7/
  │ ├── logo_24.png
  │ ├── logo_48.png
  │ └── logo.png
  │
 ...
```

## Disclaimer
Everest allows anyone to submit new assets to this repository. 
However, this does not mean that Everest is in direct partnership with any project.

Everest will reject projects that are deemed as a scam or fraudulent after review. 
Everest reserves the right to change the terms of asset submissions at any time due to changing market conditions, risk of fraud, or any other factors we deem relevant.