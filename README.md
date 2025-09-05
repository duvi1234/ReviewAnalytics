# ReviewAnalytics - Amazon Product Review Sentiment Analysis

A modern web application that analyzes sentiment from Amazon product reviews using AI-powered insights. Built with React frontend and Flask backend.

![ReviewAnalytics](https://img.shields.io/badge/ReviewAnalytics-AI%20Powered-blue)
![React](https://img.shields.io/badge/React-18.0.0-blue)
![Flask](https://img.shields.io/badge/Flask-2.0.0-green)
![Python](https://img.shields.io/badge/Python-3.8+-blue)

## 🚀 Features

- **Product Search**: Search for any product on Amazon to get comprehensive reviews
- **AI Sentiment Analysis**: Advanced sentiment analysis with polarity scoring
- **Interactive Charts**: Beautiful pie charts showing sentiment distribution
- **Modern UI**: Clean, responsive design with glassmorphism effects
- **Real-time Analysis**: Instant sentiment analysis of customer reviews
- **Review Display**: Detailed review cards with sentiment indicators

## 📋 Table of Contents

- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Installation](#-installation)
- [Usage](#-usage)
- [API Documentation](#-api-documentation)
- [Project Structure](#-project-structure)
- [Contributing](#-contributing)
- [License](#-license)

## 🛠 Tech Stack

### Frontend
- **React 18** - Modern UI framework
- **Tailwind CSS** - Utility-first CSS framework
- **Chart.js** - Interactive charts and graphs
- **React Chart.js 2** - React wrapper for Chart.js

### Backend
- **Flask** - Python web framework
- **BeautifulSoup4** - Web scraping library
- **ScraperAPI** - Professional web scraping service
- **TextBlob** - Natural language processing
- **Flask-CORS** - Cross-origin resource sharing

## 📦 Installation

### Prerequisites
- Python 3.8 or higher
- Node.js 16 or higher
- npm or yarn

### Backend Setup

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd major_major
   ```

2. **Navigate to backend directory**
   ```bash
   cd backend
   ```

3. **Create virtual environment**
   ```bash
   python -m venv venv
   ```

4. **Activate virtual environment**
   ```bash
   # On Windows
   venv\Scripts\activate
   
   # On macOS/Linux
   source venv/bin/activate
   ```

5. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

6. **Set up environment variables**
   Create a `.env` file in the backend directory:
   ```env
   SCRAPER_API_KEY=your_scraper_api_key_here
   ```

7. **Run the backend server**
   ```bash
   python app.py
   ```
   The backend will run on `http://localhost:5000`

### Frontend Setup

1. **Navigate to frontend directory**
   ```bash
   cd frontend
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Start the development server**
   ```bash
   npm start
   ```
   The frontend will run on `http://localhost:3000`

## 🎯 Usage

### Web Application

1. **Open your browser** and go to `http://localhost:3000`
2. **Enter a product name** in the search bar (e.g., "iPhone", "laptop", "headphones")
3. **Click Search** to analyze reviews
4. **View results**:
   - Sentiment distribution chart
   - Detailed review cards
   - Sentiment analysis scores

### API Usage

#### Get Product Reviews
```bash
GET /api/reviews?product=<product_name>
```

**Example:**
```bash
curl "http://localhost:5000/api/reviews?product=iphone"
```

**Response:**
```json
{
  "product": "iphone",
  "query_type": "search",
  "reviews": [
    {
      "product": "Apple iPhone 13",
      "review": "Great phone with excellent camera quality...",
      "title": "Product Review",
      "rating": null,
      "sentiment": "positive",
      "polarity": 0.8
    }
  ],
  "total_reviews": 15
}
```

## 📚 API Documentation

### Endpoints

#### `GET /api/reviews`
Retrieves product reviews with sentiment analysis.

**Parameters:**
- `product` (required): Product name to search for

**Response:**
- `product`: Product name
- `query_type`: Type of query (always "search")
- `reviews`: Array of review objects
- `total_reviews`: Total number of reviews

**Review Object:**
- `product`: Product name
- `review`: Review text
- `title`: Review title
- `rating`: Product rating (if available)
- `sentiment`: Sentiment label ("positive", "negative", "neutral")
- `polarity`: Sentiment polarity score (-1 to 1)

#### `GET /`
Health check endpoint.

**Response:**
```json
{
  "message": "Amazon Review Scraper API is running!",
  "usage": {
    "search_by_name": "/api/reviews?product=iphone"
  }
}
```

## 📁 Project Structure

```
major_major/
├── backend/
│   ├── app.py                 # Main Flask application
│   ├── requirements.txt      # Python dependencies
│   ├── scrapers/
│   │   └── scraper_api.py   # Amazon scraping logic
│   └── sentiment.py          # Sentiment analysis module
├── frontend/
│   ├── public/
│   │   └── index.html       # HTML template
│   ├── src/
│   │   ├── App.js           # Main React component
│   │   ├── index.js         # React entry point
│   │   ├── index.css        # Global styles
│   │   └── components/
│   │       ├── SearchBar.js      # Search input component
│   │       ├── ReviewsList.js   # Reviews display component
│   │       └── SnetimentChart.js # Chart component
│   ├── package.json         # Node.js dependencies
│   └── tailwind.config.js   # Tailwind configuration
└── README.md               # This file
```

## 🔧 Configuration

### Environment Variables

Create a `.env` file in the backend directory:

```env
SCRAPER_API_KEY=your_scraper_api_key_here
```

### ScraperAPI Setup

1. Sign up at [ScraperAPI](https://www.scraperapi.com/)
2. Get your API key from the dashboard
3. Add the API key to your `.env` file

## 🚀 Deployment

### Backend Deployment

1. **Using Heroku:**
   ```bash
   # Install Heroku CLI
   heroku create your-app-name
   git push heroku main
   ```

2. **Using Python Anywhere:**
   - Upload your backend files
   - Set up a web app
   - Configure environment variables

### Frontend Deployment

1. **Build for production:**
   ```bash
   cd frontend
   npm run build
   ```

2. **Deploy to Netlify/Vercel:**
   - Connect your GitHub repository
   - Set build command: `npm run build`
   - Set publish directory: `build`

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🐛 Troubleshooting

### Common Issues

1. **ScraperAPI Key Error:**
   - Ensure your `.env` file is in the backend directory
   - Verify your ScraperAPI key is valid

2. **CORS Errors:**
   - Make sure the backend is running on port 5000
   - Check that Flask-CORS is properly configured

3. **No Reviews Found:**
   - Try different product names
   - Check if the product has reviews on Amazon
   - Verify your ScraperAPI plan allows the required requests

4. **Frontend Not Loading:**
   - Ensure all dependencies are installed (`npm install`)
   - Check if the backend is running
   - Verify the API URL in the frontend code

### Debug Mode

Run the backend with debug mode enabled:
```bash
python app.py
```

Check the console for detailed error messages and API request logs.

## 📞 Support

If you encounter any issues or have questions:

1. Check the [Troubleshooting](#-troubleshooting) section
2. Review the [API Documentation](#-api-documentation)
3. Open an issue on GitHub

## 🔮 Future Enhancements

- [ ] Support for multiple e-commerce platforms
- [ ] Advanced filtering options
- [ ] Export functionality
- [ ] User authentication
- [ ] Review history tracking
- [ ] Mobile app development

---

**Made with ❤️ by Durga Devi R**

*This project is for educational purposes. Please respect Amazon's terms of service and use responsibly.*
