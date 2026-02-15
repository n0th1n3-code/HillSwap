# 🏛️ HillSwap Educational Interface

**Educational DeFi demonstration tool for Congressional staff**

⚠️ **IMPORTANT: This is an EDUCATIONAL TOOL ONLY. Not for actual cryptocurrency trading.**

## Overview

HillSwap is a modified fork of the Uniswap Interface designed to help Congressional staff understand:
- How decentralized exchanges operate
- Compliance monitoring mechanisms in DeFi
- OFAC sanctions screening implementation
- Role of blockchain analytics companies
- Regulatory challenges in cryptocurrency

## Key Features

### Educational Components
- **Compliance Monitoring Notices** at every transaction step
- **Educational Overlay** explaining DeFi concepts
- **Mandatory Disclaimer Page** with ethics reminders
- **Testnet-Only Mode** (mainnet disabled)

### Compliance Demonstrations
- OFAC sanctions screening simulation
- Transaction monitoring checklists
- Analytics provider information
- Blockchain immutability warnings

## Installation

### Prerequisites
- Node.js 16+ and Yarn
- Git

### Setup

1. **Clone the repository**
```bash
git clone https://github.com/[your-org]/hillswap.git
cd hillswap
```

2. **Install dependencies**
```bash
yarn install
```

3. **Start development server**
```bash
yarn start
```

4. **Build for production**
```bash
yarn build
```

## File Structure

```
hillswap/
├── src/
│   ├── components/
│   │   ├── EducationalOverlay/      # Top banner with educational info
│   │   ├── WalletModal/
│   │   │   └── ComplianceNotice.tsx # Wallet connection warning
│   │   ├── swap/
│   │   │   └── ComplianceBanner.tsx # Swap screen compliance info
│   │   └── TransactionConfirmation/
│   │       └── ComplianceInfo.tsx   # Transaction checklist
│   ├── pages/
│   │   ├── Disclaimer/              # Mandatory disclaimer page
│   │   └── Send/
│   │       └── ComplianceSection.tsx # Send screen compliance info
│   ├── constants/
│   │   └── hillswap.ts              # Configuration constants
│   └── assets/
│       └── svg/
│           └── capitol-dome.svg     # HillSwap logo
├── public/
│   └── index.html                   # Update title/meta tags
└── package.json                     # Update name/description
```

## Implementation Guide

### 1. Replace Branding

**Update package.json:**
- Change `name` to `"hillswap"`
- Update `description` to include educational disclaimer

**Update public/index.html:**
```html
<title>HillSwap - Educational DeFi Interface</title>
<meta name="description" content="Educational DeFi interface for Congressional staff - Not for actual trading" />
```

**Replace logo:**
- Save `capitol-dome.svg` to `src/assets/svg/`
- Update logo imports throughout the app

**Find and replace:**
- "Uniswap" → "HillSwap" (case-sensitive)
- Update all references in components and documentation

### 2. Add Components

Copy the provided components into your project:

1. **EducationalOverlay** → `src/components/EducationalOverlay/index.tsx`
2. **DisclaimerPage** → `src/pages/Disclaimer/index.tsx`
3. **WalletComplianceNotice** → `src/components/WalletModal/ComplianceNotice.tsx`
4. **SwapComplianceBanner** → `src/components/swap/ComplianceBanner.tsx`
5. **TransactionComplianceInfo** → `src/components/TransactionConfirmation/ComplianceInfo.tsx`
6. **SendComplianceSection** → `src/pages/Send/ComplianceSection.tsx`
7. **Constants** → `src/constants/hillswap.ts`

### 3. Integrate Components

**In your main App.tsx:**
```typescript
import { EducationalOverlay } from './components/EducationalOverlay';

function App() {
  return (
    <>
      <EducationalOverlay />
      {/* Rest of your app */}
    </>
  );
}
```

**Add disclaimer routing:**
```typescript
import { DisclaimerPage } from './pages/Disclaimer';

// In your router configuration:
<Route path="/disclaimer" element={<DisclaimerPage />} />

// Check disclaimer acceptance on app load:
useEffect(() => {
  const accepted = localStorage.getItem('hillswap_disclaimer_accepted');
  if (!accepted && window.location.pathname !== '/disclaimer') {
    navigate('/disclaimer');
  }
}, []);
```

**In WalletModal component:**
```typescript
import { WalletComplianceNotice } from './ComplianceNotice';

// Add before wallet connection buttons:
<WalletComplianceNotice />
```

**In Swap component:**
```typescript
import { SwapComplianceBanner } from './ComplianceBanner';

// Add at top of swap interface:
<SwapComplianceBanner />
```

**In Transaction Confirmation:**
```typescript
import { TransactionComplianceInfo } from './ComplianceInfo';

// Add in confirmation modal:
<TransactionComplianceInfo />
```

**In Send page:**
```typescript
import { SendComplianceSection } from './ComplianceSection';

// Add at top of send form:
<SendComplianceSection />
```

### 4. Update Theme Colors

In your theme configuration file (e.g., `src/theme/index.tsx`):

```typescript
export const colors = {
  primary: '#1C3F94',    // Congressional blue
  secondary: '#B31942',  // Flag red
  background: '#F8F9FA',
  // ... other colors
};
```

### 5. Configure Testnet Only

Update your network configuration to disable mainnet:

```typescript
// In your network config file
export const SUPPORTED_NETWORKS = [
  {
    chainId: 11155111,
    name: 'Sepolia',
    type: 'testnet',
  },
  // Remove or comment out mainnet
  // { chainId: 1, name: 'Ethereum', type: 'mainnet' },
];
```

## Ethics Compliance

### For Congressional Staff

Before engaging with cryptocurrency in ANY capacity:

1. **Consult Ethics Committee**
   - House: ethicscommittee@mail.house.gov
   - Senate: ethics@ethics.senate.gov

2. **Review Requirements**
   - STOCK Act implications
   - Financial disclosure requirements ($1,000+ threshold)
   - Conflict of interest considerations
   - Transaction reporting requirements

3. **Understand Restrictions**
   - Ethics rules may prohibit certain crypto activities
   - Legislative work may create conflicts of interest
   - Disclosure requirements are mandatory

## Educational Resources

- [OFAC Sanctions Programs](https://ofac.treasury.gov/sanctions-programs-and-country-information)
- [FinCEN Virtual Currency Guidance](https://www.fincen.gov/resources/statutes-and-regulations/guidance)
- [SEC Digital Assets Framework](https://www.sec.gov/digital-assets)
- [CFTC Virtual Currencies](https://www.cftc.gov/Bitcoin/index.htm)
- [GAO Cryptocurrency Reports](https://www.gao.gov/cryptocurrency)

## Compliance Monitoring Overview

This interface demonstrates how real exchanges implement compliance:

### Wallet Connection Phase
- OFAC sanctions screening
- Geolocation verification
- VPN/proxy detection
- Historical activity analysis

### Transaction Execution Phase
- Source/destination address screening
- Token contract validation
- Liquidity pool compliance
- Real-time monitoring activation

### Post-Transaction Phase
- Blockchain indexing
- Pattern analysis
- Regulatory reporting triggers
- Law enforcement intelligence

## Testing

This interface should ONLY be used with testnets:
- Sepolia (Ethereum)
- Goerli (Ethereum)
- Mumbai (Polygon testnet)

**Never connect to mainnet or use real funds.**

## Contributing

This is an educational project. Contributions should focus on:
- Improving educational content
- Adding compliance information
- Enhancing clarity of explanations
- Updating regulatory information

## License

GPL-3.0-or-later (inherits from Uniswap Interface)

## Disclaimer

This software is provided "as is" for educational purposes only. It is not intended for actual cryptocurrency trading. Congressional staff must consult appropriate ethics committees before engaging with cryptocurrency. The creators assume no liability for misuse of this educational tool.

## Support

For questions about:
- **Technical issues**: Open a GitHub issue
- **Ethics compliance**: Contact House/Senate Ethics Committee
- **Regulatory questions**: Consult your Legislative Counsel

---

**Remember: This is an educational demonstration tool. Do not use for actual trading.**
