# ProductsAndCategories
В базе данных MS SQL Server есть продукты и категории. Одному продукту может соответствовать много категорий, в одной категории может быть много продуктов. Напишите SQL запрос для выбора всех пар «Имя продукта – Имя категории». Если у продукта нет категорий, то его имя все равно должно выводиться.

SELECT
    P.ProductName AS 'Имя продукта',
    COALESCE(C.CategoryName, 'Без категории') AS 'Имя категории'
FROM
    Products P
LEFT JOIN
    ProductCategory PC ON P.ProductID = PC.ProductID
LEFT JOIN
    Categories C ON PC.CategoryID = C.CategoryID;

