# Introduction

`maple-js` is a comprehensive and user-friendly JavaScript SDK for Maple Protocol. It is designed to enable seamless interaction with Maple Protocol's smart contracts on Ethereum. This SDK equips developers with the essential tools to integrate with the Maple Protocol ecosystem, simplifying the process of connecting to the blockchain, managing accounts, submitting transactions, and handling events generated by smart contracts.

Utilizing the JavaScript SDK for Maple Protocol allows developers to efficiently create robust and secure dApps that leverage the full potential of Maple Protocol's smart contracts, fostering innovation and driving the adoption of decentralized finance solutions.

Whether you are building backend services, frontend applications, or a combination of both, the Maple SDK provides the tools you need to create a seamless user experience.

# Exports

| Export                 | Purpose                                                                                 |
| ---------------------- | --------------------------------------------------------------------------------------- |
| `addresses`            | Contains the contract addresses for different networks (mainnet, testnet)               |
| `bPool`                | Manages Balancer liquidity pool functionality                                           |
| `chainlink`            | Manages Chainlink oracle functionality                                                  |
| `ContractTypes`        | Enumerates different contract types in the Maple Protocol ecosystem                     |
| `erc20`                | Standard ERC20 token contract functionality                                             |
| `fixedTermLoanManager` | Manages fixed-term loan creation and management functionality                           |
| `loanManager`          | Manages loan creation and management functionality                                      |
| `loanV5`               | Implements the latest loan functionality                                                |
| `MapleAddressMapping`  | Mapping of contract addresses to their respective types in the Maple Protocol ecosystem |
| `mapleGlobalsV2`       | Manages global settings and configurations for Maple Protocol (version 2)               |
| `mapleGlobalsV2V2`     | Manages global settings and configurations for Maple Protocol (version 2.2)             |
| `mapleRewards`         | Manages rewards distribution in the Maple Protocol ecosystem                            |
| `mapleToken`           | Implements the Maple Protocol token functionality                                       |
| `openTermLoan`         | Implements open-term loans functionality                                                |
| `openTermLoanManager`  | Manages open-term loan creation and management functionality                            |
| `poolManager`          | Manages pool creation and management functionality                                      |
| `poolManagerV2`        | Manages pool creation and management functionality (version 2)                          |
| `poolV2`               | Manages liquidity pools in the Maple Protocol ecosystem (version 2)                     |
| `uniswapRouterV2`      | Manages Uniswap V2 router functionality                                                 |
| `withdrawalManager`    | Manages withdrawal functionality in the Maple Protocol ecosystem                        |
| `xmpl`                 | Implements the XMPL token functionality                                                 |

Depending on a Smart contract package structure, the SDK export might include different properties, such as `core`, `factory`, `initializer`, `deployer`, which can be accessible through the export. For example, the `openTermLoan` export includes the following properties:

```js
const openTermLoan = {
  core: openTermLoanImports.MapleLoan__factory,
  factory: openTermLoanImports.MapleLoanFactory__factory,
  initializer: openTermLoanImports.MapleLoanInitializer__factory,
};
```