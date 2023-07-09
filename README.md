# Travel Log

## Overview
This script allows you to create a travel log by adding details of countries visited along with the number of visits and cities traveled to within each country. The information is stored in a list called `travel_log` as dictionaries.

## Usage
1. Initialize an empty `travel_log` list.

2. Use the `add_new_country` function to add country information to the travel log.

    ```python
    add_new_country(country, visit, cities)
    ```

    - `country` (str): Name of the country you visited.
    - `visit` (str): Number of times you visited the country.
    - `cities` (list): List of cities you traveled to within the country.

3. Prompt the user for the number of countries they want to add (`cont_visit`).

4. Inside a loop, gather the country details for each iteration:

    a. Prompt the user for the country name, number of visits, and number of cities visited.

    b. Inside a nested loop, collect the names of the cities visited for that country.

    c. Call the `add_new_country` function to add the country details to the `travel_log` list.

5. After adding all the countries, the updated `travel_log` list will be printed.

## Example
Here's an example of how to use the code:

```python
travel_log = []

def add_new_country(country, visit, cities):
    new_visit = {}
    new_visit["country"] = country
    new_visit["visits"] = visit
    new_visit["cities"] = cities
    travel_log.append(new_visit)

cont_visit = int(input("How many countries do you want to add? "))

for _ in range(cont_visit):
    cities = []
    country = input("Enter the name of the country you visited: ")
    visits = input(f"Enter the number of times you visited {country}: ")
    visits_city = int(input(f"How many cities did you visit? "))
    for _ in range(visits_city):
        city = input("Enter the name of the city you traveled to: ")
        cities.append(city)

    add_new_country(country, visits, cities)

print(travel_log)
