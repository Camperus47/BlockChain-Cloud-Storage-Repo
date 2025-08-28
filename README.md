# DecentralDrive - Decentralized Image Sharing Platform

A modern, decentralized image upload and sharing platform built with React, Solidity, and IPFS. Store your images on the blockchain with advanced access control features.

## 🌟 Features

- **Decentralized Storage**: Images stored on IPFS for immutable, distributed access
- **Smart Contract Security**: Ethereum smart contracts manage ownership and permissions
- **Access Control**: Grant/revoke access to specific users for your images
- **Modern UI**: Beautiful, responsive interface with smooth animations
- **MetaMask Integration**: Seamless Web3 wallet connectivity
- **File Validation**: Support for images up to 10MB with type validation
- **Real-time Updates**: Dynamic gallery updates and status tracking

## 🚀 Quick Start

### Prerequisites

- Node.js (v16 or higher)
- MetaMask browser extension
- Pinata account for IPFS storage

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd decentralized-image-sharing
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Environment Setup**
   ```bash
   cp .env.example .env
   ```
   
   Fill in your environment variables:
   ```env
   VITE_PINATA_API_KEY=your_pinata_api_key
   VITE_PINATA_SECRET_API_KEY=your_pinata_secret_key
   VITE_CONTRACT_ADDRESS=deployed_contract_address
   ```

4. **Compile Smart Contract**
   ```bash
   npm run compile
   ```

5. **Deploy Smart Contract**
   ```bash
   # Local deployment
   npm run deploy
   
   # Testnet deployment (Sepolia)
   npm run deploy:sepolia
   ```

6. **Start Development Server**
   ```bash
   npm run dev
   ```

## 🔧 Configuration

### Pinata Setup

1. Create an account at [Pinata.cloud](https://pinata.cloud)
2. Generate API keys from your dashboard
3. Add the keys to your `.env` file

### Smart Contract Deployment

1. Update `hardhat.config.js` with your network settings
2. Add your private key and RPC URLs to `.env`
3. Deploy using the provided scripts

## 📱 Usage

### Connecting Wallet
- Click "Connect Wallet" to link your MetaMask
- Ensure you're on the correct network

### Uploading Images
1. Select an image file (PNG, JPG, GIF up to 10MB)
2. Add a description
3. Click "Upload to Blockchain"
4. Confirm the transaction in MetaMask

### Viewing Images
- Your images appear automatically in the gallery
- Enter another user's address to view their public images

### Access Control
- Click on your images to manage permissions
- Grant access to specific wallet addresses
- Revoke access as needed

## 🏗️ Architecture

```
src/
├── components/
│   ├── Header.tsx          # Navigation and wallet connection
│   ├── FileUpload.tsx      # Image upload functionality
│   └── ImageGallery.tsx    # Image display and management
├── utils/
│   ├── contract.ts         # Smart contract interactions
│   └── ipfs.ts             # IPFS/Pinata integration
├── types/
│   └── index.ts            # TypeScript definitions
└── artifacts/              # Compiled contract artifacts
```

## 🔐 Smart Contract

The `ImageStorage.sol` contract provides:

- **Image Upload**: Store IPFS hashes with metadata
- **Ownership Tracking**: Each image linked to uploader's address
- **Access Control**: Grant/revoke permissions to specific users
- **Data Retrieval**: Query images and permissions efficiently

### Key Functions

```solidity
function uploadImage(string memory _ipfsHash, string memory _description)
function grantAccess(address _user, string memory _ipfsHash)
function revokeAccess(address _user, string memory _ipfsHash)
function getUserImages(address _user) returns (string[] memory)
function getImageDetails(string memory _ipfsHash) returns (ImageData memory)
```

## 🎨 UI/UX Features

- **Glass Morphism**: Modern frosted glass effects
- **Gradient Backgrounds**: Beautiful color transitions
- **Smooth Animations**: Hover effects and micro-interactions
- **Responsive Design**: Works on all device sizes
- **Loading States**: Clear feedback during operations
- **Error Handling**: User-friendly error messages

## 🔒 Security

- **Access Control**: Smart contract enforces permissions
- **Input Validation**: File type and size restrictions
- **Error Handling**: Comprehensive error management
- **MetaMask Integration**: Secure transaction signing

## 📦 Dependencies

### Frontend
- React 18 with TypeScript
- Ethers.js for blockchain interaction
- Tailwind CSS for styling
- Lucide React for icons

### Blockchain
- Hardhat development environment
- Solidity smart contracts
- OpenZeppelin security libraries

### Storage
- IPFS via Pinata for decentralized storage
- Immutable content addressing

## 🚀 Deployment

### Frontend Deployment
```bash
npm run build
```

### Smart Contract Networks
- Local: Hardhat Network
- Testnet: Sepolia
- Mainnet: Ethereum Mainnet

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License.

## 🆘 Support

For issues and questions:
- Check the troubleshooting section
- Open an issue on GitHub
- Review the documentation

## 🔗 Links

- [IPFS Documentation](https://docs.ipfs.io/)
- [Pinata API Docs](https://docs.pinata.cloud/)
- [Ethereum Development](https://ethereum.org/developers/)
- [MetaMask Documentation](https://docs.metamask.io/)