# StockVision AI News - Installation Guide

This document provides detailed instructions for setting up and running the StockVision AI News application.

## System Requirements

- **Node.js**: v18.0.0 or higher (LTS version recommended)
- **npm**: v8.0.0 or higher (comes with Node.js)
- **Operating System**: Windows, macOS, or Linux

## Installation Steps

### 1. Clone the Repository

```bash
git clone <repository-url>
cd stock-vision-ai-news
```

### 2. Install Dependencies

The project uses npm for package management. All dependencies are specified in the `package.json` file.

```bash
npm install
```

This will install all required dependencies, including:

- React & React DOM
- TypeScript
- Vite (build tool)
- shadcn/ui components
- Tailwind CSS
- Recharts (for data visualization)
- React Router DOM
- TanStack Query
- And other UI libraries and utilities

### 3. Start the Development Server

```bash
npm run dev
```

This will start the development server at [http://localhost:5173](http://localhost:5173) by default.

### 4. Build for Production (Optional)

If you want to build the application for production:

```bash
npm run build
```

The built files will be in the `dist` directory.

## Troubleshooting Common Issues

### Node Version Issues

If you encounter errors related to Node.js version compatibility, try using nvm (Node Version Manager) to install the correct version:

```bash
# Install nvm (if not already installed)
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.5/install.sh | bash

# Install Node.js LTS
nvm install --lts

# Use the LTS version
nvm use --lts
```

### Package Installation Errors

If you encounter errors during package installation:

1. Delete the `node_modules` directory and `package-lock.json` file:
   ```bash
   rm -rf node_modules package-lock.json
   ```

2. Clear npm cache:
   ```bash
   npm cache clean --force
   ```

3. Reinstall dependencies:
   ```bash
   npm install
   ```

### Port Conflicts

If port 5173 is already in use, Vite will automatically try to use the next available port. You can also specify a different port:

```bash
npm run dev -- --port 3000
```

## Additional Configuration

### Environment Variables

For future API integrations, you'll need to set up environment variables. Create a `.env` file in the root directory:

```
VITE_API_KEY=your_api_key_here
VITE_NEWS_API_KEY=your_news_api_key_here
```

Note: All environment variables used with Vite must be prefixed with `VITE_`.

## Using a Different Package Manager

### Using Yarn

If you prefer using Yarn:

```bash
# Install Yarn
npm install -g yarn

# Install dependencies
yarn

# Start development server
yarn dev

# Build for production
yarn build
```

### Using pnpm

If you prefer using pnpm:

```bash
# Install pnpm
npm install -g pnpm

# Install dependencies
pnpm install

# Start development server
pnpm dev

# Build for production
pnpm build
```

## Next Steps

After installation, refer to the following resources:

- [README.md](README.md) - For an overview of the project
- [TODO.md](TODO.md) - For planned features and improvements 