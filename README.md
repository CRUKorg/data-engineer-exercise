# CRUK Data Engineer assignment
Thank you for taking the time to participate in this assignment! 

This is a technical exercise we use at CRUK to evaluate potential new data engineers. It will allow you to demonstrate that you know how to: 

* Acquire and explore a dataset
* Ingest data
* Transform data
* Query data

Please read all the instructions below carefully and don’t hesitate to contact us if you have any queries.

We are expecting you to spend no more than a few hours on this exercise.  You may find some parts challenging.  If you don't reach the end of the exercise, please share with us where you got to.

The instructions below request some additional information in addition to your code.  Please include these in a `README.md` file in your answer.

## Instructions

### Context
You have been given the following user story to implement:

> As a data analyst
>
> I want to query the [New York City Taxi cab Data Set](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page)
>
> So that I can answer the questions: 
>
> *"What is the average speed in miles per hour across all trips in March 2021?"*
> Reminder:  average speed = total distance travelled / total time taken
>
> _"In each week for the month of March 2021, what are the top 5 Pick up locations (`PULocationID`) 
> that result in trips which are slower than the average speed for a trip in the month 
> (regardless of drop off and pick up locations)?"_

At CRUK, we mainly use Snowflake as our Data Warehouse, with supporting technologies provided by AWS (e.g. S3 and ECS).  We work mainly in Python and SQL.  We use infrastructure as code frameworks like AWS CDK (Cloud Development Kit) to create and maintain our AWS infrastructure. 

### Guidance

For this exercise we are ideally looking for an implementation that aligns with the technologies above.  If you wish to use Snowflake, a free trial Snowflake account can be obtained at https://signup.snowflake.com/   Alternatively you may also use a database running locally such as SQL Server Express, PostgreSQL, etc.

We would prefer a solution that uses SQL for the query/analysis section, however if using any database is problematic given the tech/devices you currently have access to, then this exercise can also be attempted using pure Python, however please describe in the `README.md` in pseudo-SQL the query that you would write for the query/analysis part of the exercise.

We are not expecting use of the AWS CDK in this exercise.

We will not penalise a solution that runs locally without using any cloud technologies, but please include notes in the `README.md` file explaining how you would move your workload into cloud services such as Snowflake and AWS, with some thoughts on how your implementation will scale.

### Data

Download the NYC Yellow taxi data set for March 2021 (from the exercise repo or from [https://d37ci6vzurychx.cloudfront.net/trip-data/yellow_tripdata_2021-03.parquet](https://d37ci6vzurychx.cloudfront.net/trip-data/yellow_tripdata_2021-03.parquet) ). *Note that we only want the "Yellow" set, and for March 2021.*

### What we want you to do

Write code to perform the following tasks:

* **INGEST**

  * Read/ingest the data from the NYC yellow taxi file.
  * You should ideally only ingest the columns needed to answer the exercise question.
  * If using a database, please include your table definition in a file named `table.sql`.

* **TRANSFORM**

  * You need to correct a known data quality issue where Location ID 161 and Location 237 have been accidentally swapped in the source system. *You need to renumber them*.

* **QUERY** 

  * Write a query to answer the exercise questions

     > *"What is the average speed in miles per hour for trips in March 2021?"*
     
     > *In each week for the month of March 2021, what are the top 5 Pick up locations (PULocationID)* 
     > *that result in trips which are slower than the average trip speed in the whole month* 
     > *(regardless of drop off and pick up locations)?*

  You will need to deal with some data quality issues.  *When calculating the average speed, you should discard any invalid rows which would make the calculation invalid.*

* **WORKING AND RESULTS**

  Save all Python code used for sharing with us.  Also save and share a copy of the query SQL in a file named `query.sql` and a copy of the results in a file named `results.txt `.


## What we're looking for
Things we value in your solution are:
* _Self-explanatory code_ – the solution should include some code comments that allow the code to speak for itself without long paragraphs of explanation.
* _Simplicity_ – Layers of abstraction, patterns, or similar architectural features aren’t needed.

Your solution should include:

1. Instructions about your strategy and important decisions you made.  Include these in the `README.md` file.
2. The `README.md` should also answer the following questions:
* How did you ensure data quality?
* What would need to change for the solution scale to work with a 1TiB dataset with new data arriving each day?
3. Your submission should be a zip file containing your solution and the requested documentation, or a link to your GitHub repository.
4. Your submission needs to contain everything we need to run the code (scripts etc.)

## What happens after this?
We hope you succeed in this exercise!  If so, we'll arrange an interview, part of which will include you demonstrating your solution from your device.  You'll show it running, and walk us through it while we discuss the choices that you made and any challenges you faced.

*Good Luck!*

