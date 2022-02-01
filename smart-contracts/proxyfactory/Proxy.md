# Proxy

A completely transparent, and thus interface-less, proxy contract.

\


## Constructor

The constructor requires at least one of \`factory\_\` or \`implementation\_\`. If an implementation is not provided, the factory is treated as an IDefaultImplementationBeacon to fetch the default implementation.

```solidity
    constructor(
        address factory_,
        address implementation_
    );
```

#### Parameters:

| Index |        Name       |    Type   | Internal Type | Description                                                       |
| :---: | :---------------: | :-------: | :-----------: | ----------------------------------------------------------------- |
|   0   |     `factory_`    | `address` |   `address`   | The address of a proxy factory, if any.                           |
|   1   | `implementation_` | `address` |   `address`   | The address of the implementation contract being proxied, if any. |

\
