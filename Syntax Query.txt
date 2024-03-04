CREATE TABLE kimiafarma.analytic AS
SELECT
  ft.transaction_id,
  ft.date,
  ft.branch_id,
  kc.branch_name,
  kc.kota,
  kc.provinsi,
  kc.rating AS rating_cabang,
  ft.customer_name,
  pr.product_id,
  pr.product_name,
  pr.price AS actual_price,
  ft.discount_percentage,
  CASE
    WHEN pr.price <= 50000 THEN '10%'
    WHEN pr.price <= 100000 THEN '15%'
    WHEN pr.price <= 300000 THEN '20%'
    WHEN pr.price <= 500000 THEN '25%'
    ELSE '30%'
  END AS persentase_gross_laba,
  ROUND(pr.price * (1 - ft.discount_percentage), 0) as nett_sales,
  CASE
    WHEN pr.price <= 50000 THEN ROUND(pr.price * (1 - ft.discount_percentage) * 0.1, 0)
    WHEN pr.price <= 100000 THEN ROUND(pr.price * (1 - ft.discount_percentage) * 0.15, 0)
    WHEN pr.price <= 300000 THEN ROUND(pr.price * (1 - ft.discount_percentage) * 0.2, 0)
    WHEN pr.price <= 500000 THEN ROUND(pr.price * (1 - ft.discount_percentage) * 0.25, 0)
    ELSE ROUND(pr.price * (1 - ft.discount_percentage) * 0.3, 0)
  END AS nett_profit,
  ft.rating AS rating_transaksi
FROM
  kimiafarma.final_transaction ft
JOIN
  kimiafarma.kantor_cabang kc
  ON ft.branch_id = kc.branch_id
JOIN 
  kimiafarma.product pr
  ON ft.product_id = pr.product_id;