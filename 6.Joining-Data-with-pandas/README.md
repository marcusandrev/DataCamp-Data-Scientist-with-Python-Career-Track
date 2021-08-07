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
- Counting missing rows with left join
    - Note: A left join will return all of the rows from the left table. If those rows in the left table match multiple rows in the right table, then all of those rows will be returned. Therefore, the returned rows must be equal to if not greater than the left table. Knowing what to expect is useful in troubleshooting any suspicious merges.
- Right join to find unique movies
    - movies_and_scifi_only = movies.merge(scifi_only, left_on="id", right_on="movie_id")
    - how to subset for missing dataframes notes:
        - action_movies = movie_to_genres[movie_to_genres["genre"]== "Action"]
- Popular genres with right join
    - genres_movies = movie_to_genres.merge(pop_movies, how='right', 
                                      left_on="movie_id", 
                                      right_on="id")
- Using outer join to select actors
    - iron_1_and_2 = iron_1_actors.merge(iron_2_actors,
                                     on="id",
                                     how="outer",
                                     suffixes=('_1','_2'))
- Self join
    - merging tables together
    - crews.merge(crews, on='id', how='inner',
                                suffixes=('_dir','_crew'))
- How does pandas handle self joins?
- Index merge for movie ratings
- Do sequels earn more?

## Advance Merging and Concantenating
- Steps of a semi-join
- Performing an anti-join
    - empl_cust = employees.merge(top_cust, on='srid', 
                            how='left', indicator=True)
    - srid_list = empl_cust.loc[empl_cust['_merge'] == 'left_only', 'srid']
    - print(employees[employees['srid'].isin(srid_list)])
- Performing a semi-join
- Concatenation basics
    - tracks_from_albums = pd.concat([tracks_master,tracks_ride,tracks_st],
                               sort=True)
    - tracks_from_albums = pd.concat([tracks_master,tracks_ride,tracks_st],
                               ignore_index=True,
                               sort=True)
    - tracks_from_albums = pd.concat([tracks_master,tracks_ride,tracks_st],
                               join="inner",
                               sort=True)
- Concatenating with keys
    - inv_jul_thr_sep = pd.concat([inv_jul,inv_aug,inv_sep], 
                            keys=["7Jul", "8Aug", "9Sep"])
- Using the append method
    - metallica_tracks = tracks_ride.append([tracks_master, tracks_st], sort=False)
- Concatenate and merge to find common songs

## Merging Ordered and Time-Series Data
- Correlation between GDP and S&P500
    - gdp_sp500 = pd.merge_ordered(gdp, sp500, left_on='Year', right_on='Date', 
                             how='left',  fill_method='ffill')
- Phillips curve using merge_ordered()
- merge_ordered() caution, multiple columns
    - date_ctry = pd.merge_ordered(gdp, pop, on=["country","date"], fill_method="ffill")