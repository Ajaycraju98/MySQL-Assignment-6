# MySQL-Assignment-6
This  Assignment explains about the Joins and Unions in MySQL
- Consider the Country table and Persons table that you created earlier and perform the following:
select * from country;
select * from persons;

 --(1)Perform inner join, Left join, and Right join on the tables. 
#innerjoin
select c.Id,c.Country_name,c.Population,p.Id,p.Population,p.F_name,p.Country_name from country as c
inner join persons as p on c.Country_name=p.Country_name;
#leftjoin
select c.Id,c.Country_name,c.Population,p.Id,p.Population,p.Country_name from country as c
left join persons as p on c.Country_name=p.Country_name;
#right join 
select c.Id,c.Country_name,c.Population,p.Id,p.Population,p.Country_name from country as c
right join persons as p on c.Country_name=p.Country_name;

-- (2)List all distinct country names from both the Country and Persons tables. 
select Id,Country_name from country union select Id,Country_name from persons;

-- (3)List all country names from both the Country and Persons tables, including duplicates. 
select Id,Country_name from country union all select Id,Country_name from persons;

-- (4)Round the ratings of all persons to the nearest integer in the Persons table.
SELECT F_name, Rating, ROUND(Rating, 0) AS Rounded_rating FROM persons;
