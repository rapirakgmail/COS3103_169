1. ติดตั้ง classicmodels database : classicmodels_psql_14.sql
2. สร้าง customer_order_count View:
    CREATE OR REPLACE VIEW classicmodels.customer_order_count AS
      	SELECT
      	    c.customernumber,
      	    c.customername,
      	    COUNT(o.ordernumber) AS order_count
      	FROM classicmodels.customers c
      	JOIN classicmodels.orders o
      	    ON c.customernumber = o.customernumber
      	GROUP BY
      	    c.customernumber,
      	    c.customername
      	ORDER BY
      	    c.customernumber;
3.import project
      1. import "maven" project
      2. update dependency "pom.xml"
         
