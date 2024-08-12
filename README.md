
#Review 1
##1. List all the Canadian cities and their populations
'''SELECT * FROM north_american_cities WHERE Country = "Canada";'''

##2. Order all the cities in the United States by their latitude from north to south
'''SELECT * from north_american_cities
WHERE Country = "United States"
ORDER BY latitude Desc;'''

##3. List all the cities west of Chicago, ordered from west to east
'''SELECT * from north_american_cities
WHERE longitude < (SELECT longitude FROM north_american_cities WHERE City = "Chicago") 
ORDER BY longitude;'''

##4. List the two largest cities in Mexico (by population)
'''SELECT * FROM north_american_cities 
WHERE Country = "Mexico"
ORDER BY population DESC
LIMIT 2;'''

##5. List the third and fourth largest cities (by population) in the United States and their population
'''SELECT * FROM north_american_cities 
WHERE Country = "United States"
ORDER BY population DESC
LIMIT 2
OFFSET 2;'''
