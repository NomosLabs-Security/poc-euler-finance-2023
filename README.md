# Euler Finance donateToReserves Flash Loan Exploit — PoC

> **Educational Purpose Only** — This PoC is created for security research and education
> purposes only. It runs against a fork, not mainnet.

## Quick Start

```bash
git clone https://github.com/NomosLabs-Security/poc-euler-finance-2023
cd poc-euler-finance-2023
forge test -vvvv
```

## Details

- **Exploit Date:** 2023-03-13
- **Fork Block:** #16818044 (one block prior)
- **Expected Output:** Flash loan donateToReserves() exploit, self-liquidation profit
- **Full Analysis:** [NomosLabs Security Intelligence Archive](https://nomoslabs.io/archive/euler-finance-2023)

## Description

The donateToReserves() function in Euler Finance's eToken contract reduced the user's
collateral without performing a health check. Combined with a flash loan, this enabled:

1. Open a large position (via flash loan)
2. Zero out collateral via donateToReserves()
3. Self-liquidate (using a second account)
4. Profit from the liquidation bonus

## RPC Providers

```
Alchemy:   https://eth-mainnet.alchemyapi.io/v2/YOUR_KEY
Infura:    https://mainnet.infura.io/v3/YOUR_KEY
QuickNode: https://YOUR_ENDPOINT.quiknode.pro/YOUR_KEY
```

## License

MIT — For educational use only.
