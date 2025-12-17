# CosmicRelay

Built for Base

CosmicRelay is a Base-oriented repository designed to provide a clear signal of Base network availability, wallet connectivity, and RPC correctness using official Coinbase tooling.

The repository intentionally focuses on infrastructure validation rather than application-specific logic, making it suitable for repeated Base environment checks.

## Project Intent

CosmicRelay is used to:
- Validate Base Mainnet and Base Sepolia connectivity
- Exercise wallet onboarding via OnchainKit
- Perform deterministic, read-only onchain queries using Viem
- Surface clear Basescan references for transparency and verification

## Supported Networks

Base Mainnet  
chainId (decimal): 8453  
Explorer: https://basescan.org  
RPC: https://mainnet.base.org  

Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  
RPC: https://sepolia.base.org  

## Application Behavior

Primary file: app/cosmicRelay.ts

At runtime, the application:
- Initializes an OnchainKitProvider bound to the selected Base chain
- Renders wallet connection UI
- Uses Viem to query:
  - RPC-reported chainId
  - latest block number
  - native ETH balance for a provided address
- Exposes Basescan explorer URLs for inspection

## Repository Structure

app/  
- cosmicRelay.ts  
  React entry component combining wallet UX with Base JSON-RPC reads.

Expected companion files:
- package.json
- tsconfig.json
- index.html / main.tsx
- .env (optional)

## Libraries

OnchainKit  
Wallet UI components and Base-first primitives  
https://github.com/coinbase/onchainkit  

Viem  
EVM client for Base JSON-RPC reads  

## Installation and Usage

Requirements:
- Node.js 18+
- Browser environment with wallet support

Install dependencies using your preferred package manager and run the project with a standard React/Vite or Next.js development server.

Optional environment variables:
- VITE_BASE_RPC_URL
- VITE_BASE_SEPOLIA_RPC_URL

## Base Mainnet Deployment

Deployed on Base Mainnet

Network: Base Mainnet  
chainId (decimal): 8453  
Explorer: https://basescan.org  

Deployed contract address:  
your_adress  

Basescan deployment and verification links:
- https://basescan.org/address/your_adress  
- https://basescan.org/address/your_adress#code  

## License

MIT License

## Author

GitHub: https://github.com/secular-eaglet  
Public contact (email): secular-eaglet0s@icloud.com  
Public contact (X): https://x.com/Silvanadks31  

## Testnet Deployment (Base Sepolia)

As part of pre-production validation, one or more contracts may be deployed to the Base Sepolia test network to confirm correct behavior and tooling compatibility.

Network: Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  

Contract "errors" address:  
0xf171f83eddc0bb041d094f280d531ea5696cb26e  

Deployment and verification:
- https://sepolia.basescan.org/address/0xf171f83eddc0bb041d094f280d531ea5696cb26e  
- https://sepolia.basescan.org/0xf171f83eddc0bb041d094f280d531ea5696cb26e/0#code  

Contract "Exercise" address (optional):  
0x89cc512f1c6afe97124ed65d57f852e25c7a4994  

Deployment and verification:
- https://sepolia.basescan.org/address/0x89cc512f1c6afe97124ed65d57f852e25c7a4994  
- https://sepolia.basescan.org/0x89cc512f1c6afe97124ed65d57f852e25c7a4994/0#code  

Contract "ERC20" address (optional):  
0xb46f58df84ff97cdeae27db7bb4289a27a01b780  

Deployment and verification:
- https://sepolia.basescan.org/address/0xb46f58df84ff97cdeae27db7bb4289a27a01b780  
- https://sepolia.basescan.org/0xb46f58df84ff97cdeae27db7bb4289a27a01b780/0#code 
These testnet deployments provide a controlled environment for validating Base tooling, account abstraction flows, and read-only onchain interactions prior to Base Mainnet usage.
