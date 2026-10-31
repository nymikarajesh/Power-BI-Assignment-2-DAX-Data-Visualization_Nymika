# Power-BI-Assignment-2-DAX-Data-Visualization_Nymika
E-Commerce Sales Analysis -DAX (Data Analysis Expressions) to analyze and transform e-commerce sales data, generating key metrics and insights.
New Column	Purpose
Category Type	-Combines Category and Sub-Category --- Category Type = 'Order Details'[Category] & "-" & 'Order Details'[Sub-Category]
Revenue per Order	- Amount × Quantity ---- Revenue = 'Order Details'[Amount]*'Order Details'[Quantity]
Sales Category-	Above Average / Below Average - IF(
    'Order Details'[Amount] >
    CALCULATE(
        AVERAGE('Order Details'[Amount]),
        ALL('Order Details')
    ),
    "Above Average",
    "Below Average"
)
Order Count =
DISTINCTCOUNT('Order Details'[Order ID])
Average Profit in Delhi =
CALCULATE(
    AVERAGE('Order Details'[Profit]),
    'List of Orders'[City] = "Delhi")
    YTD Sales =
CALCULATE(SUM('Order Details'[Amount]),
    DATESYTD('List of Orders'[Order Date]))
Max Profit Margin =
MAXX(
    'Order Details',
    DIVIDE(
        'Order Details'[Profit],
        'Order Details'[Amount],
        0
    )
)

Charts created based on requirement
