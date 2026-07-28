**International Call Percentage**

SELECT

&#x20;   ROUND(

&#x20;       100.0 \* SUM(

&#x20;           CASE

&#x20;               WHEN c.country\_id <> r.country\_id THEN 1

&#x20;               ELSE 0

&#x20;           END

&#x20;       ) / COUNT(\*),

&#x20;       1

&#x20;   ) AS international\_calls\_pct

FROM phone\_calls p

JOIN phone\_info c

&#x20;   ON p.caller\_id = c.caller\_id

JOIN phone\_info r

&#x20;   ON p.receiver\_id = r.caller\_id;

