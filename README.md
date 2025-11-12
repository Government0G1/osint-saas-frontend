# osint-saas-frontend

React frontend for OSINT SaaS Platform - Phase 1: MVP with unified search interface, social media footprint mapping visualization, breach data display, and metadata extraction results.

## 📋 Project Overview

Modern, responsive React SPA for the OSINT (Open Source Intelligence) platform. Provides intuitive interface for conducting comprehensive open-source investigations with geospatial visualizations and real-time data aggregation.

**Phase 1 Focus**: MVP User Interface (0-6 months)
- Unified search interface
- Social footprint mapping with geospatial overlays
- Breach data visualization dashboard
- Metadata display & export

## 🛠 Tech Stack

- **Framework**: React 18+ (with Hooks)
- **Styling**: Tailwind CSS
- **Maps & Visualization**: Mapbox GL JS
- **State Management**: React Context API / Redux (Phase 2)
- **HTTP Client**: Axios
- **Build Tool**: Vite
- **Testing**: Vitest, React Testing Library
- **Forms**: React Hook Form
- **UI Components**: Headless UI, Radix UI

## 📁 Project Structure

```
osint-saas-frontend/
├── src/
│   ├── components/
│   │   ├── SearchBar.jsx         # Main search input component
│   │   ├── ResultTable.jsx       # Results display table
│   │   ├── MapOverlay.jsx        # Mapbox geospatial visualization
│   │   ├── BreachAlert.jsx       # Breach data display
│   │   ├── MetadataViewer.jsx    # Metadata extraction results
│   │   └── Navigation.jsx        # Header/sidebar navigation
│   ├── pages/
│   │   ├── Home.jsx              # Landing/dashboard page
│   │   ├── SearchResults.jsx     # Search results page
│   │   ├── About.jsx             # About page
│   │   └── Documentation.jsx     # API documentation
│   ├── hooks/
│   │   ├── useSearch.js          # Custom search hook
│   │   ├── useMapbox.js          # Mapbox integration
│   │   └── useFetch.js           # Generic data fetching
│   ├── services/
│   │   ├── api.js                # API client configuration
│   │   └── auth.js               # Authentication service
│   ├── styles/
│   │   └── tailwind.css          # Tailwind configuration
│   ├── App.jsx                   # Main app component
│   └── main.jsx                  # React entry point
├── public/
│   └── index.html                # HTML template
├── .env.example                  # Environment variables
├── tailwind.config.js            # Tailwind configuration
├── vite.config.js                # Vite configuration
├── package.json                  # Dependencies
└── README.md                     # This file
```

## 🚀 Quick Start

### Prerequisites
- Node.js 16+
- npm or yarn
- Backend API running (see osint-saas-backend)

### Installation

1. **Clone repository**
   ```bash
   git clone https://github.com/Government0G1/osint-saas-frontend.git
   cd osint-saas-frontend
   ```

2. **Install dependencies**
   ```bash
   npm install
   # or
   yarn install
   ```

3. **Setup environment**
   ```bash
   cp .env.example .env.local
   # Edit .env.local with backend API URL and Mapbox token
   ```

4. **Run development server**
   ```bash
   npm run dev
   # or
   yarn dev
   ```

Application will be available at `http://localhost:5173`

## 📚 Core Components

### SearchBar Component
- Multi-field search (username, email, domain, phone)
- Real-time search suggestions
- Advanced filter options
- Search history

### ResultTable Component
- Sortable data table
- Expandable rows for details
- Export to CSV/JSON
- Result pagination

### MapOverlay Component
- Geospatial visualization of results
- Location clustering
- Interactive markers
- Heat maps for density analysis

### BreachAlert Component
- Breach detection results
- Risk severity indicators
- Timeline view
- Historical breach data

### MetadataViewer Component
- EXIF data display
- Document metadata
- Archive information
- Formatted export options

## 🧪 Testing

```bash
# Run tests
npm run test

# Run with coverage
npm run test:coverage

# Watch mode
npm run test:watch
```

## 🏗 Building for Production

```bash
# Build optimized bundle
npm run build

# Preview production build
npm run preview

# Analyze bundle size
npm run analyze
```

## 📦 Docker

```bash
# Build image
docker build -t osint-saas-frontend .

# Run container
docker run -p 3000:80 osint-saas-frontend
```

## 🔑 Environment Variables

```env
VITE_API_BASE_URL=http://localhost:8000/api
VITE_MAPBOX_TOKEN=your_mapbox_token
VITE_APP_ENV=development
```

## 🎨 UI/UX Guidelines

- Responsive design (mobile-first)
- Accessibility (WCAG 2.1 AA)
- Dark mode support
- Intuitive navigation
- Real-time feedback
- Error handling

## 📖 Documentation

- [Component Documentation](./docs/COMPONENTS.md)
- [API Integration Guide](./docs/API_INTEGRATION.md)
- [Styling Guide](./docs/STYLING.md)

## 🤝 Contributing

1. Fork the repository
2. Create feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open Pull Request

## 📜 License

MIT License - See [LICENSE](./LICENSE) file

## 👥 Team

- **Project Lead**: [@Government0G1](https://github.com/Government0G1)

## 📧 Support

- [GitHub Issues](https://github.com/Government0G1/osint-saas-frontend/issues)
- [GitHub Discussions](https://github.com/Government0G1/osint-saas-frontend/discussions)

## 🎯 Roadmap

- **Phase 1 (0-6 months)**: MVP UI with core features ✓
- **Phase 2 (6-18 months)**: Advanced analytics, ML predictions
- **Phase 3 (18-36 months)**: Enterprise dashboard, custom dashboards

See [Strategic Roadmap Project](https://github.com/users/Government0G1/projects/1) for detailed tracking.
