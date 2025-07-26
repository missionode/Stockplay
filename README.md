# Stock Prediction Dashboard

A web-based application for analyzing and predicting stock market performance. Users can search for companies, classify stocks as successful or unsuccessful using a logistic regression-based formula, and generate price predictions for successful stocks with visualizations.

## Description

This dashboard allows users to:
- Search for listed companies using a filterable search bar.
- Classify the stock as successful or unsuccessful based on historical data (using metrics like CAGR and Sharpe Ratio).
- For successful stocks, predict future prices using a linear regression model (with stub for advanced ARIMA-GARCH).
- Visualize historical and predicted prices with interactive charts and tables.

The app is built with HTML, Tailwind CSS for styling, JavaScript for logic, and Chart.js for visualizations. It uses the Financial Modeling Prep (FMP) API for fetching stock data.

## Features

- **Search Bar**: Real-time, filterable company search with suggestions, keyboard navigation, and inline loading spinner.
- **Classification**: Determines stock success using a simplified logistic regression model.
- **Prediction**: Generates future price forecasts with line charts (historical in blue, predicted in purple dashed lines).
- **Visualizations**: Interactive charts and tables for data exploration.
- **UX Enhancements**: Dark mode support, animations (e.g., flip-in for results, pulse for suggestions), color coding (green for success, red for failure), and accessibility features (ARIA labels).
- **Error Handling**: User-friendly messages for API failures, no results, or insufficient data, with retry buttons.

## Installation and Setup

### Prerequisites
- A modern web browser (e.g., Chrome, Firefox).
- A free API key from Financial Modeling Prep (FMP): Sign up at [https://site.financialmodelingprep.com/register](https://site.financialmodelingprep.com/register).

### Local Setup
1. Clone the repository:
   ```
   git clone https://github.com/your-username/stock-prediction-dashboard.git
   cd stock-prediction-dashboard
   ```
2. Open `index.html` in a text editor and replace `YOUR_FMP_API_KEY` with your actual FMP API key.
3. Serve the app locally (to avoid CORS issues):
   - Install a simple server: `npm install -g serve`
   - Run: `serve -s .`
   - Access at `http://localhost:3000`.

### GitHub Pages Deployment
1. Push the code to a GitHub repository.
2. Go to repository Settings > Pages.
3. Set Source to `Deploy from a branch`, select `main` or `gh-pages`, and choose `/ (root)`.
4. Access the live app at `https://<username>.github.io/<repository-name>`.

Note: For CORS issues on GitHub Pages, the code includes a temporary proxy (`https://cors-anywhere.herokuapp.com/`). Request access at [https://cors-anywhere.herokuapp.com/corsdemo](https://cors-anywhere.herokuapp.com/corsdemo). For production, set up a custom proxy or backend.

## Usage

1. Open the app in your browser.
2. Search for a company (e.g., "GOOGL" for Google/Alphabet).
3. Select a suggestion from the dropdown (use arrow keys and Enter for keyboard navigation).
4. View the classification result (successful/unsuccessful with probability).
5. If successful, explore historical and predicted charts, table, and update via date range (stubbed for now).

Example: Search "AAPL" → Classified as successful → Predicted prices shown in charts.

## API Configuration

- **Financial Modeling Prep (FMP)**: Used for symbol search and historical data.
  - Search Endpoint: `/v3/search?query={query}&limit=10&apikey={key}`
  - Historical Endpoint: `/v3/historical-price-full/{symbol}?apikey={key}`
- Replace the API key in the code to enable data fetching.
- Free tier limits: 500MB bandwidth/month; suitable for testing.

If the API fails (e.g., invalid key), the app shows an error with a retry button.

## Technologies Used

- **Frontend**: HTML5, Tailwind CSS (for responsive styling), JavaScript (ES6+).
- **Libraries**: Chart.js (for charts).
- **API**: Financial Modeling Prep (FMP).
- **Deployment**: GitHub Pages.

## Limitations and Improvements

- Prediction uses basic linear regression; integrate server-side ARIMA-GARCH for better accuracy.
- Date range picker is stubbed; future updates can fetch dynamic data.
- No real-time data; relies on historical closes.
- Contributions welcome: Fork and submit PRs for features like advanced models or more APIs.

## Contributing

1. Fork the repository.
2. Create a feature branch: `git checkout -b feature/new-feature`.
3. Commit changes: `git commit -m 'Add new feature'`.
4. Push: `git push origin feature/new-feature`.
5. Open a Pull Request.

## License

MIT License. See [LICENSE](LICENSE) for details.

---

For questions or issues, open a GitHub issue or contact the maintainer. Last updated: July 27, 2025.
