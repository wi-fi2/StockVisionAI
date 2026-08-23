# StockVision AI News

StockVision AI News is a modern React application that provides real-time stock market data visualization, AI-powered market predictions, and financial news analysis. It's built with a tech stack focused on performance and a great user experience.

![StockVision AI News Dashboard](https://via.placeholder.com/1200x600/0A0E17/8B5CF6?text=StockVision+AI+Dashboard)

## Features

- **Real-Time Stock Tracking**: Search and monitor stock prices with detailed metrics
- **Interactive Charts**: Visualize stock performance with customizable time ranges (1W, 1M, 1Y, 5Y)
- **AI Market Predictions**: AI-powered analysis of market trends and stock movements
- **Market News Analysis**: Financial news with AI-analyzed sentiment and impact assessment
- **Market Overview**: Quick dashboard showing overall market performance with caching for improved performance
- **Technical Analysis**: In-depth technical indicators (SMA, EMA, RSI, MACD) with optimized caching
- **Top Movers**: Track the biggest daily gainers and losers

## Performance Optimizations

- **Advanced Caching System**: Multi-tier caching (memory, localStorage, sessionStorage) for market data and technical analysis
- **Data Persistence**: Stock and analysis data persist across page reloads
- **API Call Optimization**: Reduced API calls through strategic caching with configurable TTL (Time-To-Live)
- **Throttled Requests**: API request throttling to prevent rate limit issues

## Tech Stack

- **Framework**: React with TypeScript
- **Build Tool**: Vite
- **UI Components**: shadcn/ui
- **Styling**: Tailwind CSS
- **Charts**: Recharts
- **Routing**: React Router DOM
- **Data Fetching**: TanStack Query
- **API Integration**: Alpha Vantage for market data, Google Gemini for AI analysis

## Getting Started

### Prerequisites

- Node.js (v18 or later recommended)
- npm or yarn package manager

### Installation

1. Clone the repository:

```bash
git clone <repository-url>
cd stock-vision-ai-news
```

2. Install dependencies:

```bash
npm install
# or
yarn install
```

3. Set up environment variables:

Copy the `.env.example` file to `.env` and fill in your API keys:

```bash
cp .env.example .env
```

Then edit the `.env` file with your API keys:

```
VITE_GEMINI_API_KEY=your-gemini-api-key
VITE_ALPHA_VANTAGE_API_KEY=your-alpha-vantage-api-key
```

4. Start the development server:

```bash
npm run dev
# or
yarn dev
```

5. Open [http://localhost:5173](http://localhost:5173) in your browser to see the application.

## Project Structure

```
stock-vision-ai-news/
├── public/              # Static assets
├── src/                 # Source code
│   ├── components/      # UI components
│   │   └── ui/          # shadcn/ui components
│   ├── hooks/           # Custom React hooks
│   ├── lib/             # Utility functions and constants
│   ├── pages/           # Application pages
│   ├── services/        # API services and data fetching
│   │   ├── alphaVantageService.ts    # Stock market data service
│   │   ├── cacheService.ts           # Multi-tier caching service
│   │   ├── geminiService.ts          # AI analysis service
│   │   └── stockService.ts           # Stock data processing
│   ├── utils/           # Helper utilities
│   ├── App.tsx          # Main application component
│   └── main.tsx         # Application entry point
├── index.html           # HTML entry point
├── tailwind.config.ts   # Tailwind CSS configuration
├── vite.config.ts       # Vite configuration
└── tsconfig.json        # TypeScript configuration
```

## Key Components

- **MarketOverview**: Displays overall market indices, sector performance, and popular stocks with efficient caching
- **TechnicalAnalysis**: Provides detailed technical indicators and signals for stocks with symbol and timeframe-specific caching
- **StockChart**: Interactive price charts with multiple timeframes
- **NewsCard**: Latest financial news with AI sentiment analysis
- **AIPredictions**: AI-generated market forecasts and stock predictions

## Caching Implementation

The application implements a sophisticated multi-tier caching system to improve performance and reduce API calls:

1. **In-Memory Cache**: Fastest access for current session
2. **SessionStorage**: Persists data across page reloads
3. **LocalStorage**: Longer-term persistence with TTL (Time-To-Live)

Cached data includes:
- Market overview data (15-minute TTL)
- Technical analysis by symbol and timeframe (10-minute TTL)
- Stock chart data
- News data

Each component includes a refresh button to force-fetch fresh data when needed.

## Important Notes

- The application uses Google's Gemini API to generate news and market insights.
- You'll need Alpha Vantage API keys for stock data (the free tier has limitations)
- See the `.env.example` file for all required API keys

## Customization

### Theme

The application uses Tailwind CSS for styling with a custom dark theme. You can modify the theme in `tailwind.config.ts` to adjust colors, spacing, and other design elements.

### Adding New Features

To add new features, follow these steps:

1. Create new component files in the `src/components` directory
2. Add new API services in the `src/services` directory
3. Update the Dashboard page in `src/pages/Dashboard.tsx` to include your new components

## Deployment

To build the application for production:

```bash
npm run build
# or
yarn build
```

The build artifacts will be stored in the `dist/` directory and can be deployed to any static site hosting service like Vercel, Netlify, or GitHub Pages.

## Development Commands

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build locally
- `npm run lint` - Lint the codebase

## Troubleshooting

- **API Rate Limits**: If you encounter "Rate limit exceeded" errors, the application will automatically throttle requests. Consider upgrading your API plan for production use.
- **Cache Issues**: To clear all cached data, use the browser's developer tools to clear localStorage and sessionStorage.
- **UI Rendering Issues**: Make sure you're using a modern browser with JavaScript enabled.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Credits

- UI Components: [shadcn/ui](https://ui.shadcn.com/)
- Icons: [Lucide Icons](https://lucide.dev/)
- Charts: [Recharts](https://recharts.org/)
