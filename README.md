# solanaranked
# Solana Wallet Performance Ranking

A Chrome extension that detects Solana wallet addresses across websites, calculates trading performance with a gaming-inspired ranking system, and displays ranking badges next to addresses.

![Solana Ranked (1)](https://github.com/user-attachments/assets/c54a6aad-9b1e-4e60-99da-6922315db904)


## 🚀 Features

- **Automatic Wallet Detection**: Identifies Solana wallet addresses across any website you visit
- **Performance Ranking System**: Calculates wallet trading performance using a gaming-inspired tier system
- **Visual Badges**: Displays rank badges next to detected wallet addresses
- **Personal Wallet Tracking**: Add your own wallet to track your performance and progression
- **Real-time Updates**: See ranking changes as your wallet performs new trades

## 📊 Ranking System

We've implemented a game-inspired ranking system to visualize trading performance:

| Rank | Score Range | Description |
|------|-------------|-------------|
| Unranked | < 5 trades | Not enough data to rank |
| Iron | 1-19 | Beginning trader (Divisions IV-I) |
| Bronze | 20-39 | Improving trader (Divisions IV-I) |
| Silver | 40-59 | Consistent trader (Divisions IV-I) |
| Gold | 60-74 | Proficient trader (Divisions IV-I) |
| Platinum | 75-89 | Expert trader (Divisions IV-I) |
| Diamond | 90-97 | Elite trader (Divisions IV-I) |
| Master | 98-99 | Outstanding trader |
| Grandmaster | 100 | Perfect trading performance (Requires 30+ trades) |

## 🔧 Installation

### From Chrome Web Store
1. Visit the [Chrome Web Store page](#) (coming soon)
2. Click "Add to Chrome"
3. Confirm the installation

## 💻 Usage

### Viewing Wallet Rankings
1. Visit any website that displays Solana wallet addresses (explorer sites, dApps, etc.)
2. The extension will automatically detect wallet addresses and display rank badges next to them
3. Hover over a badge to see detailed performance metrics

### Adding Your Wallet
1. Click the extension icon in your browser toolbar
2. Select "Add Wallet" from the popup menu
3. Enter your Solana wallet address
4. Your wallet will now be tracked, and you'll see your own ranking and progression

### Options and Settings
1. Right-click the extension icon and select "Options"
2. Customize visibility settings, update frequency, and more

## 🔄 How Rankings Work

Rankings are calculated based on:
- **70%**: Normalized PnL (profit/loss percentage)
- **20%**: Win rate (percentage of profitable trades)
- **10%**: Trading volume

All wallets start each month at 0 points (Unranked). Points are capped based on trade count:
- 5 trades: Max 30 points (Bronze I)
- 10 trades: Max 50 points (Silver II)
- 15 trades: Max 70 points (Gold II)
- 20 trades: Max 90 points (Diamond IV)
- 30+ trades: No cap (eligible for full 100 points)

## 🔒 Privacy

- The extension only processes publicly available on-chain data
- User-added wallets are stored locally in your browser
- We do not collect any personal information or browsing history
- The extension only activates when wallet addresses are detected

## 🛠️ For Developers

### Project Structure
```
solana-wallet-ranking/
├── manifest.json           # Extension configuration
├── background.js           # Background worker for API calls
├── content_script.js       # Detects wallets and injects badges
├── popup/                  # Extension popup UI
│   ├── popup.html
│   ├── popup.css
│   └── popup.js
├── options/                # Extension options page
│   ├── options.html
│   ├── options.css
│   └── options.js
└── assets/                 # Images and resources
    └── badges/             # SVG badge templates
```

### API Integration
The extension uses a hybrid approach for data:
- **Admin-tracked wallets** (~500 addresses): Data from Helius API, updated every 4-6 hours
- **User-added wallets**: Data from public Solana RPC nodes and Jupiter API, updated every 5-15 minutes

### Contributing
1. Fork the repository
2. Create your feature branch: `git checkout -b feature/amazing-feature`
3. Commit your changes: `git commit -m 'Add some amazing feature'`
4. Push to the branch: `git push origin feature/amazing-feature`
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- [Helius](https://helius.xyz/) for providing the API for transaction data
- [Jupiter](https://jup.ag/) for DEX trade history
- [Solana](https://solana.com/) for the awesome ecosystem
