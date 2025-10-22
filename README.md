# Company Shares Outstanding Viewer

This is a single-page responsive HTML application built with Tailwind CSS that displays the maximum and minimum common stock shares outstanding for a given company, fetched from the SEC EDGAR API.

## Features

-   **Dynamic Data Fetching**: Retrieves company shares outstanding data directly from the SEC EDGAR API.
-   **CIK Parameter Support**: Load data for any 10-digit CIK by appending `?CIK=XXXXXXXXXX` to the URL.
-   **Responsive Design**: Built with Tailwind CSS for a modern, mobile-friendly interface.
-   **Max/Min Value Identification**: Clearly highlights the highest and lowest common stock shares outstanding since Fiscal Year 2021.

## Getting Started

To run this application, simply open the `index.html` file in your web browser. No special server setup is required.

### Default View

When you open `index.html` without any parameters, it will display data for **Citizens Financial Group (CIK: 0000759944)** by default.

```bash
open index.html
# or navigate to file:///path/to/index.html
```

### Viewing Data for Other Companies

You can view data for any other publicly traded company by providing its Central Index Key (CIK) as a URL parameter.

**Example:** To view data for a company with CIK `0001018724`:

```bash
open index.html?CIK=0001018724
# or navigate to file:///path/to/index.html?CIK=0001018724
```

The page will dynamically update the company name and share data without requiring a full page reload.

## Data Source

The application fetches financial data from the [SEC EDGAR API](https://www.sec.gov/edgar/sec-api-documentation).
Per SEC guidance, requests to the API should include a descriptive User-Agent. This application's client-side `fetch` requests leverage the browser's User-Agent; if a server-side proxy were used, it would be configured to set a specific User-Agent like `CFGApp/1.0 (contact@cfg.com)`.

**Important Note on CORS:**
When accessing external APIs directly from a web browser, Cross-Origin Resource Sharing (CORS) policies can sometimes prevent data fetching. While the SEC API often allows direct browser access, in a strict production environment or if you encounter issues, a server-side proxy (like [AIPipe](https://ai.pipe.sh/) or a custom backend service) would typically be employed to fetch data from the SEC and serve it to the frontend, bypassing browser CORS restrictions. This application assumes direct browser `fetch` is permissible.

## Technologies Used

-   **HTML5**: Structure
-   **Tailwind CSS**: Styling and responsiveness
-   **JavaScript (ES6+)**: Dynamic data fetching and DOM manipulation

## Attachments

This project includes the `uid.txt` file as-is, alongside the application files.