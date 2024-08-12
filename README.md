
# Review 1
## 1. List all the Canadian cities and their populations
```
SELECT * FROM north_american_cities WHERE Country = "Canada";
```

## 2. Order all the cities in the United States by their latitude from north to south
```
SELECT * from north_american_cities
WHERE Country = "United States"
ORDER BY latitude Desc;
```

## 3. List all the cities west of Chicago, ordered from west to east
```
SELECT * from north_american_cities
WHERE longitude < (SELECT longitude FROM north_american_cities WHERE City = "Chicago") 
ORDER BY longitude;
```

## 4. List the two largest cities in Mexico (by population)
```
SELECT * FROM north_american_cities 
WHERE Country = "Mexico"
ORDER BY population DESC
LIMIT 2;
```

## 5. List the third and fourth largest cities (by population) in the United States and their population
```
SELECT * FROM north_american_cities 
WHERE Country = "United States"
ORDER BY population DESC
LIMIT 2
OFFSET 2;
```


# Review 2
## 1. Find the number of movies each director has directed
```
SELECT Director, Count(Director) 
FROM movies
GROUP BY Director;
```

## 2. Find the total domestic and international sales that can be attributed to each director
```
SELECT Director, SUM(b.Domestic_Sales + b.International_sales) Total_Sales FROM MOVIES a
 LEFT JOIN boxoffice b
ON a.id = b.movie_id
```

# SQLPD
## 1.  An Illegal site’s servers were seized in a recent operation. Please submit all user’s details.
```
SELECT * FROM users;
```

## 2. An illegal site’s servers were seized in a recent operation. Please submit all users’ details. Use SQL to retrieve the data and submit the resulting table.  
```
SELECT * FROM users;
```

## 3. An Illegal site’s servers were seized in a recent operation. Please submit all users emails and number of downloads’ details
 ```
 SELECT Email, Downloads 
	FROM users;
```

## 4. An Illegal site’s servers were seized in a recent operation. Please submit all users number of downloads, emails and access times’ details. 
```
SELECT Downloads, Email, AccessTime
FROM users;
```

## 5. An Illegal site’s servers were seized in a recent operation. Please submit all users given names’ details. Please make sure there are no duplicates. 
```
SELECT DISTINCT GivenName
FROM users;
```

## 6. A mailing list of an illegal online service was sent to the SQLPD hot-line. Please submit all records’ details sorted by last names in ascending order. 
```
SELECT *
FROM mailing_list
ORDER BY LastName ASC;
```

## 7. White hat hacker has sent SQLPD exposed subscribers’ details of a shady site connected to various persons of interest. Please submit all subscribers’ details sorted by number of purchases in descending order. 
```
SELECT *
FROM subscribers
ORDER BY Purchases DESC;
```

## 8. White hat hacker has sent SQLPD exposed members’ details of a shady site connected to various persons of interest. Please submit all members usernames, names and mailing addresses’ details sorted by usernames in descending order. Please make sure there are no duplicates. 
```
SELECT DISTINCT Username, Name, MailingAddress
FROM members
ORDER BY Username DESC;
```

## 9. A mailing list of an illegal online service was sent to the SQLPD hot-line. Please submit all entries last names, join dates and first names’ details sorted by first names in descending order and then by last names in descending order. 
```
SELECT LastName, Joined, FirstName
FROM mailing_list
ORDER BY FirstName DESC, LastName DESC;
```

## 10. An illegal site’s servers were seized in a recent operation. Please submit the top 20 users’ details when sorted by last access times in ascending order and then by surnames in ascending order. 
```
SELECT *
FROM users 
ORDER BY LastAccess ASC, Surname ASC
LIMIT 20;
```
## 11. White hat hacker has sent SQLPD exposed subscribers’ details of a shady site connected to various persons of interest. Please submit the top 10 subscribers usernames and subscription dates’ details when sorted by subscription dates in ascending order and then by usernames in ascending order. Please make sure there are no duplicates. 
```
SELECT DISTINCT Username, SubscriptionDate
FROM subscribers
ORDER BY SubscriptionDate ASC, Username ASC
LIMIT 10;
```
