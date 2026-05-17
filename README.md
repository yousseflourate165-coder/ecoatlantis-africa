# 🌍 EcoAtlantis Africa - Ocean Intelligence Platform

An AI-powered environmental monitoring system for African coastal regions, designed to scale globally.

## Overview

EcoAtlantis Africa leverages artificial intelligence and satellite data to monitor pollution and environmental threats across African ocean regions in real-time. The platform provides:

- **Real-time Alerts**: Live pollution detection across African coastal zones
- **AI-Powered Analysis**: Machine learning models for environmental threat detection
- **Regional Monitoring**: Coverage across 20+ African coastal regions
- **Scalable Architecture**: Built to expand globally

## Features

✅ Africa-first regional focus with global scalability  
✅ Real-time pollution alerts system  
✅ AI-powered environmental intelligence  
✅ Interactive dashboard with region filtering  
✅ Supabase backend integration  
✅ Responsive UI with Framer Motion animations  

## Tech Stack

- **Frontend**: Next.js 14 + React 18 + TypeScript
- **Styling**: Tailwind CSS + Framer Motion
- **Backend**: Supabase (PostgreSQL)
- **Deployment**: Vercel (recommended)

## Quick Start

### Prerequisites

- Node.js 18+
- npm or yarn
- Supabase account (free tier available)

### Installation

```bash
# Clone the repository
git clone https://github.com/yousseflourate165-coder/ecoatlantis-africa.git
cd ecoatlantis-africa

# Install dependencies
npm install

# Create environment file
cp .env.local.example .env.local

# Add your Supabase credentials to .env.local

# Run development server
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## Project Structure

```
ecoatlantis-africa/
├── src/
│   ├── app/
│   │   ├── page.tsx          # Main application component
│   │   ├── layout.tsx        # Root layout
│   │   └── globals.css       # Global styles
│   ├── lib/
│   │   ├── supabase.ts       # Supabase client configuration
│   │   └── types.ts          # TypeScript type definitions
│   └── components/           # Reusable React components
├── public/                   # Static assets
├── package.json
├── tsconfig.json
├── next.config.js
├── tailwind.config.ts
└── README.md
```

## Supported African Regions

Currently monitoring 20+ regions including:
- Northern Africa: Morocco, Algeria, Tunisia, Libya, Egypt
- West Africa: Senegal, Ghana, Nigeria, Ivory Coast, Cameroon
- East Africa: Kenya, Tanzania, Ethiopia, Uganda
- Southern Africa: South Africa, Angola, Mozambique, Namibia
- Special Zones: Morocco Atlantic Coast, Gulf of Guinea

## Database Schema

### pollution_alerts table

```sql
CREATE TABLE pollution_alerts (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  zone VARCHAR(100),
  level VARCHAR(20),
  region VARCHAR(50) DEFAULT 'Africa',
  created_at TIMESTAMP DEFAULT NOW(),
  updated_at TIMESTAMP DEFAULT NOW()
);
```

## API Integration

### Fetch Alerts

```typescript
const { data, error } = await supabase
  .from('pollution_alerts')
  .select('*')
  .eq('region', 'Africa')
  .order('created_at', { ascending: false });
```

### Create Alert

```typescript
await supabase.from('pollution_alerts').insert([{
  zone: 'Gulf of Guinea',
  level: 'Critical',
  region: 'Africa'
}]);
```

## Development

```bash
# Type checking
npm run type-check

# Format code
npm run format

# Run linting
npm run lint

# Build for production
npm run build

# Start production server
npm start
```

## Deployment

### Deploy to Vercel (Recommended)

1. Push your code to GitHub
2. Import project in Vercel Dashboard
3. Add environment variables in Vercel settings
4. Deploy with one click

```bash
vercel deploy --prod
```

## Roadmap

- [ ] Real satellite data integration (Copernicus, Sentinel)
- [ ] Advanced AI models for pollution prediction
- [ ] Mobile app (React Native)
- [ ] Real-time WebSocket notifications
- [ ] Multi-language support
- [ ] Global expansion beyond Africa
- [ ] Integration with NGOs and government agencies

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

MIT License - see LICENSE file for details

## Support

For questions or issues, please open a GitHub issue or contact the team.

## Acknowledgments

- Africa's coastal communities
- Environmental monitoring organizations
- Open-source community

---

**Built with ❤️ for Africa's Ocean** 🌊