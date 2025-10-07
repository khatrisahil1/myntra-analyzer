
# 🛍️ Myntra Analyzer

A Python-based automation and analytics project to **scrape, clean, and analyze product data from [Myntra](https://www.myntra.com)**.  
Built with **Selenium**, **Pandas**, and **OpenPyXL**, this tool extracts detailed product insights — including availability, delivery, and seller comparisons — for smarter e-commerce analysis.



[![Python](https://img.shields.io/badge/Python-3.12+-blue.svg)](https://www.python.org/)
[![Selenium](https://img.shields.io/badge/Selenium-Automation-brightgreen.svg)](https://www.selenium.dev/)
[![Webdriver Manager](https://img.shields.io/badge/Webdriver--Manager-AutoSetup-orange.svg)](https://github.com/SergeyPirogov/webdriver_manager)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-yellow.svg)](https://pandas.pydata.org/)
[![OpenPyXL](https://img.shields.io/badge/OpenPyXL-Excel%20Export-lightgrey.svg)](https://openpyxl.readthedocs.io/en/stable/)
[![dotenv](https://img.shields.io/badge/dotenv-Env%20Config-informational.svg)](https://pypi.org/project/python-dotenv/)


## ✨ Features

✅ **Automated Scraping** – Extracts product data directly from Myntra using Selenium  
✅ **Bulk Mode** – Supports scraping multiple product URLs via Excel input  
✅ **Availability & Seller Insights** – Detects product availability for a given pincode, identifies nearby sellers, shows expected delivery date, and lists unique sellers offering the same product — helping users find the cheapest available option  
✅ **Data Cleaning** – Converts raw scraped data into a structured, analysis-ready format  
✅ **Excel Export** – Automatically saves processed results into `.xlsx` format  
✅ **Custom Configuration** – Easily configure URL, pincode, and output file path through `.env`


## 🧠 Project Structure
```
myntra-analyzer/
│
├── data/
│   ├── Dataset_20k.xlsx          # Sample URL dataset
│   └── myntra_output_one.xlsx    # Output from scraper
│
├── src/
│   ├── myntra_scraper_one.py     # Single product scraper
│   ├── myntra_scraper_bulk.py    # Bulk scraper
│   └── init.py
│
├── requirements.txt              # Dependencies
├── .env                          # Environment variables (optional)
├── .gitignore
└── README.md
```


## ⚙️ Installation

1️⃣ Clone the Repository
```bash
git clone https://github.com/khatrisahil1/myntra-analyzer.git
cd myntra-analyzer
```
2️⃣ Create & Activate Virtual Environment
#### macOS / Linux
```
python3 -m venv venv
source venv/bin/activate
```
#### On Windows:
```
venv\Scripts\activate
```
3️⃣ Install Dependencies
```
pip install -r requirements.txt
```

🔧 Environment Setup
```
Create a .env file in the project root:
```

## 🚀 Usage


▶️ Single Product Scraper
```
python3 src/myntra_scraper_one.py --url "https://www.myntra.com/your-product-url"
```
▶️ Bulk Scraper
```
python3 src/myntra_scraper_bulk.py
```
▶️ Run Tests
```
pytest tests/
```

## 📊 Sample Output

| Product Name | Price  | Discount | Brand           | Availability | Expected Delivery | Seller             | Pincode |
|---------------|--------|-----------|------------------|---------------|-------------------|--------------------|----------|
| T-Shirt A     | ₹799   | 40%      | Roadster        | In Stock      | Oct 12            | SellerX            | 560037   |
| Sneakers B    | ₹1,499 | 30%      | Puma             | Multiple Sellers | Oct 10         | SellerY, SellerZ   | 560037   |
---
## 🧩 Tech Stack

| Component         | Purpose                          |
|-------------------|----------------------------------|
| Python 3.12+      | Core language                    |
| Selenium          | Web scraping & browser automation |
| Webdriver-Manager | Auto ChromeDriver setup           |
| Pandas / OpenPyXL | Data cleaning & Excel export      |
| dotenv            | Environment configuration         |



## 📈 Analytics (EDA)

Use Matplotlib or Plotly to visualize pricing trends, discounts, and brand availability.
You can perform quick exploratory data analysis on the scraped dataset:

```
import pandas as pd

df = pd.read_excel("data/Dataset_20k.xlsx")

print("Total products scraped:", len(df))
print("\nTop 5 Brands:\n", df["Brand"].value_counts().head())
print("\nAverage Discount:", df["Discount"].mean())
print("\nTop Sellers:\n", df["Seller"].value_counts().head())
```

## ⭐ Support

If you found this project helpful, please 🌟 star this repo — your support keeps it growing!
