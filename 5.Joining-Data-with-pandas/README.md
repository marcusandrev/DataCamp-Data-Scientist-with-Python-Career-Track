# Joining Data with pandas
### Course Description
Being able to combine and work with multiple datasets is an essential skill for any aspiring Data Scientist. Pandas is a crucial cornerstone of the Python data science ecosystem, with Stack Overflow recording 5 million views for pandas questions. Learn to handle multiple DataFrames by combining, organizing, joining, and reshaping them using pandas. You'll work with datasets from the World Bank and the City Of Chicago. You will finish the course with a solid skillset for data-joining in pandas.

## Data Merging Basics
- Your first inner join
    - taxi_own_veh = taxi_owners.merge(taxi_veh, on='vid', suffixes=('_own','_veh'))
- Inner joins and number of rows returned
- One-to-many classification
    One-to-one:
        - the relationship between the customers and cust_tax_info
        - the relationship between the products and inventory
    One-to-many:
        - the relationship between the customers and oders
        - the relationship between the products and orders
- One-to-many merge
- Total riders in a month
- Three table merge
- One-to-many merge with multiple tables
    - land_cen_lic = land_use.merge(census, on='ward') \
                    .merge(licenses, on='ward', suffixes=('_cen','_lic'))
    - pop_vac_lic = land_cen_lic.groupby(['ward','pop_2010','vacant'], 
                                   as_index=False).agg({'account':'count'})

## Merging Tables With Different Join Types
- Counting missing rows with left join
    - movies_financials = movies.merge(financials, on='id', how='left')
- Enriching a dataset
- Note: A left join will return all of the rows from the left table. If those rows in the left table match multiple rows in the right table, then all of those rows will be returned. Therefore, the returned rows must be equal to if not greater than the left table. Knowing what to expect is useful in troubleshooting any suspicious merges.