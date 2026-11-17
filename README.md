# Amazon product scraper

> Project from 2023, kept as it was written.

A Selenium script that searches Amazon for a term, walks the result pages and saves one row per
product to Excel.

## What it collects

Product name, price, old price, rating, review count, stock quantity, fastest delivery option,
delivery date, product information, Climate Pledge status, picture URL and product URL.

## How it works

1. Opens Chrome, signs in and pauses so that a captcha or a second sign-in step can be solved by hand.
2. Asks for a search term and a number of result pages.
3. Visits every result page, reads the product cards and writes the table with pandas.

`amazon_data_IPhone_2023-07-18.xlsx` is a sample of the output.

## Run it

```bash
pip install selenium pandas openpyxl
jupyter notebook Amazon.ipynb
```

Replace the placeholder e-mail and password in the notebook with your own (do not commit them) and
set `export_path`.

## Limits

- The CSS selectors are from July 2023. Amazon changes its pages often, so expect to update them.
- Automated access may be against Amazon's conditions of use. This was a learning exercise; for
  real use the Product Advertising API is the supported route.

## Files

| File | Content |
|---|---|
| `Amazon.ipynb` | The scraper |
| `Amazon.html` | Rendered copy of the notebook |
| `amazon_data_IPhone_2023-07-18.xlsx` | Sample output |
| `About.txt` | Original notes |
