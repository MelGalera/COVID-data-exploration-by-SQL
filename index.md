COVID Data exploration using SQL

```sql
/* add a new column date with datatype as date (the existing date column has a datatype of varchar) */ 
SELECT count(*)
FROM coviddeaths;


ALTER TABLE coviddeaths RENAME COLUMN "date" TO date_orig;
ALTER TABLE coviddeaths ADD COLUMN reporting_date date;
UPDATE coviddeaths SET reporting_date = TO_DATE(date_orig, 'DD/MM/YYYY');

ALTER TABLE covidvaccinations RENAME COLUMN "date" TO date_orig;
ALTER TABLE covidvaccinations ADD COLUMN reporting_date date;
UPDATE covidvaccinations SET reporting_date = TO_DATE(date_orig, 'DD/MM/YYYY');
```
