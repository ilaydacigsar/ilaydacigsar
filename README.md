select sku, --SUM(stock) AS TotalSum,
    MAX(CASE WHEN  LEFT("sucursal",1) = 'B' THEN stock ELSE 0 END) AS "B-CHICUREO",
    MAX(CASE WHEN  LEFT("sucursal",1) = 'C' THEN stock ELSE 0 END) AS "CHICUREO",
    MAX(CASE WHEN  LEFT("sucursal",1) = 'E' THEN stock ELSE 0 END) AS "E-Count",
    MAX(CASE WHEN  LEFT("sucursal",1) = 'L' THEN stock ELSE 0 END) AS "L-Count",
    MAX(CASE WHEN  LEFT("sucursal",1) = 'M' THEN stock ELSE 0 END) AS "B-TRAPENSES",
    MAX(CASE WHEN  LEFT("sucursal",1) = 'O' THEN stock ELSE 0 END) AS "O-Count",
    MAX(CASE WHEN  LEFT("sucursal",1) = 'T' THEN stock ELSE 0 END) AS "TRAPENSES"
from "30122022bsale"
group by sku;
