# Protocol actors guide

There are three actors in the Maple Protocol ecosystem: borrowers, lenders and pool delegates. This guide will explain how each of these actors can interact with Maple Protocol's smart contracts.

## Borrowers

Borrowers are entities that seek to obtain loans from the Maple Protocol ecosystem. They interact with the smart contracts to request loans, specify the loan terms, and provide collateral as required. Once a loan is approved, borrowers can utilize the funds for their specific needs and are responsible for repaying the loan along with any applicable interest.

**Code Example:**

```js
import { mapleGlobals } from '@maplelabs/maple-js';

const contractAddress = addresses['mainnet-prod'].MapleToken; // some borrowers specific contract
const signer = 'yourSigner';

// some borrowers specific action
const contract = mapleGlobals.core.connect(contractAddress, signer);
```

## Lenders

Lenders are individuals or entities that provide capital to the Maple Protocol ecosystem in the form of digital assets. They interact with the smart contracts to deposit their funds, which are then pooled together and made available for loans. Lenders earn interest on their deposits as borrowers repay the loans.

**Code Example:**

```js
import { mapleGlobals } from '@maplelabs/maple-js';

const contractAddress = addresses['mainnet-prod'].MapleToken; // some lenders specific contract
const signer = 'yourSigner';

// some lenders specific action
const contract = mapleGlobals.core.connect(contractAddress, signer);
```

## Delegates

Delegates are entities that play a crucial role in assessing and approving loan requests. They interact with the smart contracts to review borrowers' loan applications, perform risk assessment, and ultimately approve or reject loans based on their evaluation. Delegates may charge fees for their services and help maintain the overall stability and trustworthiness of the Maple Protocol ecosystem.

**Code Example:**

```js
import { mapleGlobals } from '@maplelabs/maple-js';

const contractAddress = addresses['mainnet-prod'].MapleToken; // some delegates specific contract
const signer = 'yourSigner';

// some delegates specific action
const contract = mapleGlobals.core.connect(contractAddress, signer);
```