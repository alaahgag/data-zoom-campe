## Question 1: Knowing docker tags

get information on Docker
```bash
doceker --help
```
get help on the "docker build" command
```bash
doceker build --help
```
Automatically remove the container when it exits:
```bash
doceker container --rm [container-name]
```
## Question 2. Understanding docker first run
Run docker with the python:3.9
```bash
docker container run -it python:3.9 bash
```
version of the package wheel : 0.42.0

## Question 3. Count records
```sql
with casted_data as(
select *, cast(lpep_pickup_datetime as date) as pickup_date,
		cast(lpep_dropoff_datetime as date) as dropoff_date
from green_tripdata
)

select count(*)
from casted_data
where pickup_date = '2019-09-18'
and dropoff_date= '2019-09-18'
```
the output: 15612

## Question 4. Longest trip for each day
```sql
with casted_data as(
select *, cast(lpep_pickup_datetime as date) as pickup_date,
		cast(lpep_dropoff_datetime as date) as dropoff_date
from green_tripdata
)

select pickup_date, max(trip_distance) as max_distance
from casted_data
group by pickup_date
order by max(trip_distance) desc
limit 1;
```
the output: 2019-09-26

## Question 5. Three biggest pick up Boroughs
