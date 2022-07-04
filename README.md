# SQL-Portfolio
Using a dataset for Covid-19 impact

```
## Covid impact for all the countries

Select location, SUM(new_cases) as total_cases, SUM(new_deaths) as total_deaths, SUM(new_deaths)/SUM(New_Cases)*100 as DeathPercentage
FROM Covid_Portfolio.coviddeaths
group by location
order by DeathPercentage desc;

```

```
## India covid impact every month

Select date, location, SUM(new_cases) as total_cases, SUM(new_deaths) as total_deaths, SUM(new_deaths)/SUM(New_Cases)*100 as DeathPercentage
FROM Covid_Portfolio.coviddeaths
Where location = "india"
##where continent is not null
Group By date
order by 1,2;

```
```
## Monthly case overview for all the countries

Select date, location, population, SUM(new_deaths) as TotalDeathCount, (sum(new_deaths)/population)* 100 as DeathPercentage
FROM Covid_Portfolio.coviddeaths
##Where location like '%states%'
Where continent is not null
and location not in('World', 'European Union', 'Europe','International','North America','South America')
Group by location, population, date
order by TotalDeathCount desc;

```
```
## Populationpercent Infection count

Select Location, Population, MAX(total_cases) as HighestInfectionCount,  Max((total_cases/population))*100 as PercentPopulationInfected
FROM Covid_Portfolio.coviddeaths
##Where location like '%states%'
Group by Location, Population,
order by PercentPopulationInfected desc;
```
```
## Populationpercent Infection monthly count

Select date, Location, Population, MAX(total_cases) as HighestInfectionCount,  Max((total_cases/population))*100 as PercentPopulationInfected
FROM Covid_Portfolio.coviddeaths
##Where location like '%states%'
Group by Location, Population, date
order by PercentPopulationInfected desc;
```

