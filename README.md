# Final Power BI Report in Financial Sales
*This is a challenge of Data Engineering NTT DATA Bootcamp in [DIO](https://web.dio.me/).* It consists in creating a final report for Data Analysis in Power BI, using [the previous project](https://github.com/GiovanyRezende/financial_report_sales_2/).

## Details Page
![image](https://github.com/user-attachments/assets/f5125f12-6f9e-4910-a472-0baca3072a34)

## Top 3 Products in Sales Page
![image](https://github.com/user-attachments/assets/6b7380bf-aa40-492d-80c1-bccf0e284e6c)

### DAX for Top 3 Products
```
total_sales = SUMX(Sheet1,[ Sales])

top3_products = CALCULATE(
    [total_sales],
    TOPN(
    3,
    ALL(Sheet1[Product]),
    [total_sales]
    ),
VALUES(Sheet1[Product])
)
```

## Other Analysis Page
![image](https://github.com/user-attachments/assets/976a2996-fbfc-4a8a-a84f-dd8c93d8690d)

### DAX for Top 3 Countries in Sales and Top 5 Months in Sales and Profit
```
total_profit = SUMX(Sheet1,[Profit])

top5_month_sales = CALCULATE(
    [total_sales],
    TOPN(
    5,
    ALL(Sheet1[Month Name]),
    [total_sales]
    ),
VALUES(Sheet1[Month Name])
)

top5_month_profit = CALCULATE(
    [total_profit],
    TOPN(
    5,
    ALL(Sheet1[Month Name]),
    [total_profit]
    ),
VALUES(Sheet1[Month Name])
)

top3_country = CALCULATE(
    [total_sales],
    TOPN(
    3,
    ALL(Sheet1[Country]),
    [total_sales]
    ),
VALUES(Sheet1[Country])
)
```

## Clustering Page
![image](https://github.com/user-attachments/assets/19121c30-bfee-42c0-bf18-993a925faca3)

