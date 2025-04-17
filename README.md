1) extract the year and month ,days
   select  extract (year from order_date)as "year",
extract (month from order_date)as "month",
extract (day from order_date)as "day"
from sales

2) Group by date
   select  extract (year from order_date)as "year",order_line,ship_mode,order_date,
extract (month from order_date)as "month",
extract (day from order_date)as "day"
from sales group by order_line, ship_mode,order_date

3) Use sum of database
   select sum(profit) as "profit" ,customer_data_id, order_date,ship_date 
from sales group by customer_data_id,order_date,ship_date

4) use Count of quantity
   select count(quantity) as "count of quantity",ship_mode 
from sales where ship_mode = 'Second Class'
group by ship_mode

5)Use ORDER BY for sorting.
select * from sales
order by sales desc limit 4

6) f.Limit results for specific time periods.
SELECT *
FROM sales
WHERE order_date BETWEEN '2016-01-01' AND '2016-12-31';
