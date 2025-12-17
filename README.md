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

GitHub: https://github.com/your-handle  
Public contact (email): your-name@proton.me  
Public contact (X): https://x.com/your-handle  

## Testnet Deployment (Base Sepolia)

As part of pre-production validation, one or more contracts may be deployed to the Base Sepolia test network to confirm correct behavior and tooling compatibility.

Network: Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  

Contract #1 address:  
your_adress  

Deployment and verification:
- https://sepolia.basescan.org/address/your_adress  
- https://sepolia.basescan.org/your_adress/0#code  

Contract #2 address (optional):  
your_adress  

Deployment and verification:
- https://sepolia.basescan.org/address/your_adress  
- https://sepolia.basescan.org/your_adress/0#code  

Contract #3 address (optional):  
your_adress  

Deployment and verification:
- https://sepolia.basescan.org/address/your_adress  
- https://sepolia.basescan.org/your_adress/0#code 
These testnet deployments provide a controlled environment for validating Base tooling, account abstraction flows, and read-only onchain interactions prior to Base Mainnet usage.
