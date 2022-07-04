# SQL-Portfolio
Using a dataset for Covid-19 impact


```
## India covid impact every month

Select date, location, SUM(new_cases) as total_cases, SUM(new_deaths) as total_deaths, SUM(new_deaths)/SUM(New_Cases)*100 as DeathPercentage
FROM Covid_Portfolio.coviddeaths
Where location = "india"
##where continent is not null
Group By date
order by 1,2;
```
