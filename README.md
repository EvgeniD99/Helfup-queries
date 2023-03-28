# Helfup-queries
All helpful queries 
#SUBQUERIES 
SELECT * FROM 

(SELECT Format(date, "hh:nn") AS hour_add, DateDiff('d',date1, date2) AS difference,
  IIF(column1 IN ('statement1', 'statement2', 'statement3', 'statement4'), 
    'desired1',
    IIF(srvlvl IN ('statement5', 'statement6'),
      'desired2',
      IIF(srvlvl IN ('statement7', 'statement8', 'statement9'),
        'desired3',
        'other'
      )
    )
  ) AS name1 , *
FROM table 1
WHERE ...
GROUP BY ....


)
# with where clause
SELECT column1,
COUNT(columne2), 
AS desired_name 
FROM table1 
WHERE column 1 IN (   SELECT column1 
                      FROM table2 
                      WHERE columen IN (1,2,3) 
GROUP BY ..
