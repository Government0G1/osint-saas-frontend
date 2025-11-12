# Client Setup & Usage Guide

## 🚀 Quick Start for End Users

This guide will help you set up and use the OSINT SaaS platform client application.

## 📋 Prerequisites

- **Node.js** 16 or higher ([Download](https://nodejs.org/))
- **npm** or **yarn** (comes with Node.js)
- **Modern Web Browser** (Chrome, Firefox, Safari, Edge)
- **Mapbox Account** (free tier available at https://mapbox.com)
- **Internet Connection**

## 🔧 Installation Steps

### Option 1: Clone from GitHub (For Developers)

```bash
# Clone the repository
git clone https://github.com/Government0G1/osint-saas-frontend.git
cd osint-saas-frontend

# Install dependencies
npm install

# Create environment file
cp .env.example .env.local
```

### Option 2: Download ZIP (For Users)

1. Visit https://github.com/Government0G1/osint-saas-frontend
2. Click the green "Code" button
3. Select "Download ZIP"
4. Extract the ZIP file to your desired location
5. Open terminal in the extracted folder
6. Run:
   ```bash
   npm install
   cp .env.example .env.local
   ```

## ⚙️ Configuration

### Step 1: Setup Environment Variables

Edit `.env.local` file with these required settings:

```env
# API Configuration
VITE_API_BASE_URL=http://localhost:8000/api
# OR for deployed backend:
VITE_API_BASE_URL=https://api.yourserver.com/api

# Mapbox Token (Get from https://account.mapbox.com/)
VITE_MAPBOX_TOKEN=pk.eyJ1IjoieW91...(your_token)

# Application Environment
VITE_APP_ENV=development
# Options: development, staging, production

# Optional: API Key (if using authentication)
VITE_API_KEY=your_api_key_here
```

### Step 2: Get Mapbox Token

1. Go to https://account.mapbox.com/
2. Sign up or log in
3. Go to "Tokens" in the left menu
4. Copy your default public token (or create a new one)
5. Paste it in `.env.local` as `VITE_MAPBOX_TOKEN`

### Step 3: Backend API Configuration

Make sure your backend is running:

```bash
# In a separate terminal, run the backend
cd ../osint-saas-backend
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
uvicorn app.main:app --reload
```

Backend will run at `http://localhost:8000`

## ▶️ Running the Application

### Development Mode

```bash
npm run dev
```

Application will open at `http://localhost:5173`

### Production Build

```bash
# Build optimized bundle
npm run build

# Preview production build
npm run preview
```

## 🎯 Using the Application

### Home Page
- Welcome screen with platform overview
- Quick start tips
- Link to search interface

### 1. Unified Search

**Access**: Click "Search" in navigation

**How to Use**:
1. Select search type from dropdown:
   - **Username** - Search by social media username
   - **Email** - Search by email address
   - **Domain** - Search by website domain
   - **Phone** - Search by phone number

2. Enter search query in the input field
3. Click "Search" or press Enter
4. Wait for results to load (progress indicator shows status)

**Results Display**:
- Table view with matching accounts/records
- Click row to expand for details
- Click "Export" button to save as CSV or JSON

### 2. Social Media Footprint Mapping

**Access**: Search results page, "Mapping" tab

**How to Use**:
1. After search results load
2. Click "View on Map" or "Mapping" tab
3. Interactive map shows:
   - Account locations
   - Connected accounts
   - Geographic clusters

**Map Controls**:
- Zoom: Mouse wheel or +/- buttons
- Pan: Click and drag
- Click markers for account details
- Filter by account type using sidebar

### 3. Breach Data Check

**Access**: Search results page, "Breaches" tab

**How to Use**:
1. Searches automatically check against breach databases
2. View breach history:
   - Breach name and date
   - Data exposed (passwords, emails, etc.)
   - Risk severity
   - Timeline view

**Actions**:
- Click "Details" for more information
- Export breach report as PDF

### 4. Metadata Extraction

**Access**: Search results page, "Metadata" tab

**How to Use**:
1. Upload files or provide URLs:
   - Images (EXIF data)
   - PDFs
   - Documents (DOCX, XLSX)
   - Archives

2. System automatically extracts:
   - Creation dates
   - Author information
   - GPS coordinates (from images)
   - Software used
   - Embedded data

3. Review extracted metadata
4. Export report

## 📱 Mobile Access

The application is fully responsive:

1. Access on mobile: `http://localhost:5173` (if on same network)
2. Or deploy to cloud: `https://yourapp.com`
3. All features work on mobile browsers

## 🔒 Security Tips

✅ **Do's**:
- Keep your `.env.local` file private (don't commit to git)
- Use strong API keys
- Enable HTTPS in production
- Keep Node.js updated
- Use official Mapbox tokens

❌ **Don'ts**:
- Don't expose API keys in frontend code
- Don't commit `.env.local` to version control
- Don't use development keys in production
- Don't share backend credentials

## 🐛 Troubleshooting

### Issue: "Cannot find module" error
**Solution**:
```bash
rm -rf node_modules package-lock.json
npm install
```

### Issue: Port 5173 already in use
**Solution**:
```bash
npm run dev -- --port 3000
```

### Issue: Mapbox not loading
**Solution**:
- Verify VITE_MAPBOX_TOKEN is set correctly
- Check token is a public token
- Verify token hasn't expired

### Issue: Backend API connection fails
**Solution**:
```bash
# Check backend is running
curl http://localhost:8000/docs

# Verify API URL in .env.local
# Should be: http://localhost:8000/api
```

### Issue: Blank search results
**Solution**:
- Check backend is running and has data
- Verify API connection in browser DevTools (F12)
- Check browser console for errors

## 🔗 API Integration

The frontend connects to backend APIs:

```
GET /api/search/unified          - Unified search
GET /api/search/email            - Email search
GET /api/search/username         - Username search
GET /api/enrichment/breaches     - Breach data
GET /api/enrichment/metadata     - Metadata extraction
GET /health                      - Health check
```

See backend [API documentation](../osint-saas-backend/docs/API.md) for details.

## 📊 Using Search Results

### Export Options

1. **CSV Format**
   - Standard spreadsheet format
   - Open in Excel, Google Sheets, etc.

2. **JSON Format**
   - Structured data format
   - Ideal for programmatic use

3. **PDF Report**
   - Formatted report for sharing
   - Includes metadata and charts

### Result Actions

- **View Details** - Click row for full record
- **Deep Dive** - Click account link to see related accounts
- **Timeline** - View activity over time
- **Export** - Save results

## 🎓 Learning Resources

- [Component Documentation](./docs/COMPONENTS.md)
- [API Integration Guide](./docs/API_INTEGRATION.md)
- [Backend API Docs](../osint-saas-backend/README.md)

## 💬 Support & Feedback

- **Issues**: https://github.com/Government0G1/osint-saas-frontend/issues
- **Discussions**: https://github.com/Government0G1/osint-saas-frontend/discussions
- **Email**: support@yourdomain.com

## 🚀 Deployment

### Deploy to Vercel (Recommended)

1. Push code to GitHub
2. Connect Vercel: https://vercel.com/new
3. Select repository
4. Add environment variables
5. Deploy!

### Deploy to Netlify

1. Build: `npm run build`
2. Deploy dist folder to Netlify
3. Add environment variables in settings

### Deploy to Docker

```bash
# Build Docker image
docker build -t osint-saas-frontend .

# Run container
docker run -p 3000:80 osint-saas-frontend
```

## 📝 License

MIT License - See [LICENSE](./LICENSE)

## 🤝 Contributing

Want to improve the client? See [CONTRIBUTING.md](./CONTRIBUTING.md)
