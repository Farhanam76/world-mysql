# world-mysql
Q = Using COUNT, get the number of cities in the USA.
A= SELECT COUNT(name)FROM city WHERE CountryCode='USA'
Q = Find out the population and life expectancy for people in Argentina.
A= SELECT Population, LifeExpectancy FROM country WHERE name='Argentina';
Q =Using IS NOT NULL, ORDER BY, and LIMIT, which country has the highest life expectancy?
A = SELECT Name FROM country WHERE LifeExpectancy IS NOT NULL ORDER BY DESC LIMIT 1; ( to double check if its the correct country:  SELECT MAX(LifeExpectancy) FROM country; the SELECT Name FROM country WHERE LifeExpectancy=83.5;
Q = Using JOIN ... ON, find the capital city of Spain.
Using JOIN ... ON, list all the languages spoken in the Southeast Asia region.
Q= Using a single query, list 25 cities around the world that start with the letter F.
A =  SELECT Name FROM city WHERE Name LIKE 'F%' LIMIT 25;
Using COUNT and JOIN ... ON, get the number of cities in China.
Q= Using IS NOT NULL, ORDER BY, and LIMIT, which country has the lowest population? Discard non-zero populations.
A= SELECT MIN(Population) AS lowestPopulation, Name  FROM count WHERE Population IS NOT NULL AND Population > 0 GROUP BY Name ORDER BY lowestPopulation ASC LIMIT 1;
Q = Using aggregate functions, return the number of countries the database contains.
A = SELECT COUNT(DISTINCT Name) FROM country;
What are the top ten largest countries by area?

Q = List the five largest cities by population in Japan.
A = SELECT Name, MAX(Population) AS population FROM city WHERE CountryCode='JPN' GROUP BY Name LIMIT 5;
List the names and country codes of every country with Elizabeth II as its Head of State. You will need to fix the mistake first!
List the top ten countries with the smallest population-to-area ratio. Discard any countries with a ratio of 0.
Q= List every unique world language.
A =  SELECT DISTINCT Language FROM countrylanguage ORDER BY Language ASC;

List the names and GNP of the world's top 10 richest countries.
List the names of, and number of languages spoken by, the top ten most multilingual countries.
Q = List every country where over 50% of its population can speak German.
A = SELECT CountryCODE FROM countrylanguage WHERE Language='German' AND Percentage > 50; then SELECT Name FROM country WHERE Code IN ('AUT', 'CHE', 'DEU', 'LIE');
Q = Which country has the worst life expectancy? Discard zero or null values.
A = SELECT Name, MIN(LifeExpectancy) AS Lowest life expectancy FROM country WHERE LifeExpectancy IS NOT NULL GROUP BY Name ORDER BY 'lowest life expectancy'LIMIT 1;
 Q = List the top three most common government forms.
 A =  SELECT (GovernmentForm) FROM country GROUP BY GovernmentForm LIMIT 3;
Q = How many countries have gained independence since records began?
A =  SELECT COUNT(DISTINCT NAME) FROM country WHERE IndepYEAR IS NOT NULL;

