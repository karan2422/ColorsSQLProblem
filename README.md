# ColorsSQLProblem
We need to write a query to get the Green-Orange if the Green exists for the same IDS &amp; if not then display the respective color if its only green.


SELECT id,
    CASE
      WHEN COUNT(DISTINCT color) = 2 THEN 'Green-orange'
      ELSE MAX(color)
    END AS COLOR
FROM colors
WHERE color IN ('green', 'Green-orange')
GROUP BY id;
