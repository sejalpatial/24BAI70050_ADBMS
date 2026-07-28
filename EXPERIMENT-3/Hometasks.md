**Final Account Balance**



SELECT

&#x20;   account\_id,

&#x20;   SUM(

&#x20;       CASE

&#x20;           WHEN transaction\_type = 'Deposit' THEN amount

&#x20;           WHEN transaction\_type = 'Withdrawal' THEN -amount

&#x20;       END

&#x20;   ) AS final\_balance

FROM transactions

GROUP BY account\_id;

