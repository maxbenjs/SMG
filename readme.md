# SMG | GDT – BI Dev Challenge
---

This provides an overview of the my work for the GDT BI Dev Challenge. The structure of the readme is written to provide the assessors of the task an overview of the approach that was taken including decisions regarding tooling/environments, references to the files for relevant answers, general notes as well as some of challenges.


### Files in Repo
---

- GDT – BI Dev Challenge Folder: Folder containing dataset, instructions, erd
- credentials_v2.json: Credentials required to progammatically access GCP (private_key_id & private_key removed for security)
- 1_big_query_dev_environment.ipynb: Testing environment notebook to create BigQuery Client & create test datasets and tables
- 2.1_smg_recreate_fct_listings.ipynb: Notebook which contains reasoning and code used to recreate fct_listings.csv 
- 2_smg_challenge_create_tables.ipynb: Notebook which contains list of table paramater jsons, and Python code to create tables
- 3_smg_challenge_a.ipynb: Notebook to challenge a
- 4_smg_challenge_b.ipynb: Notebook to challenge b
- 5_smg_challenge_c.ipynb: Notebook to challenge c



### Tools Used
---

- Given the use of BigQuery, DBT, Looker, GCP, SQL and Python for this role I wanted to demonstrate ability within key components of SMGs Techstack
- Whilst the easiest solution would have been Google Sheets, I didn't deem this to sufficiently demonstrate the skills required in the job
- Python & SQL were a priority for me to use through-out the challenge
- I decided to use Python to progammatically access GCP / BigQuery instead of relying on their respective GUIs
- Ultimately, I didn't end up using DBT or Looker
    - Whilst I was keen to use DBT, it was a time constraint trade off between Python for the GCP/BigQuery work or DBT
    - Given that DBT is an intuitive tool, I decided to emphasises Python, specifically for the programmatic working with GCP/BigQuery
    - I considered using Looker Studio, but didn't think the visualisations in this challenge required a BI Tool. There was also a time consideration. You will have to take my word that I am highly experienced and proficient in Looker, despite not using it here
    
  

### Development Environment
---

- All of the workings and analysis are displayed in Jupter Notebooks
- I used the BigQuery UI to test the tables once they had been created as well as to wrirte the queries that we're then used in Jupyter Notebooks




### General Notes
---
- Data quality was mostly good, although key columns in certain dimension tables we're missing, despite being requested as a dimension on which to analyse/visualise the data
    - If this wasn't planned, it would be worth updating for future candidates
    - Specific cases we're these issues arouse are documented within the relevant sections of the Notebooks
    - There were a couple of unusual rows of data within fct_listings, which lead me to recreate the csv before creating the table. Again this is mentioned in the specific notebook (1_smg_recreate_fct_listings)
- Dataset size: The fct_listings records was less than expected. Similarly I found that the data within cln_listings, didn't lead to any changes to fct_listings when creating the type 2 dimension modelling.


#### Type 2 Dimension Modelling (Challenge A, Task1)
- The most challenging aspect of the task and where I don't have 100% confidence in the answer
- In creating the merge statement, I discovered what I deemed errors in fct_listins, which lead me to recreate the dataset
- Whilst the merge statement ran without error, the data within cln_listings didn't allow for row inserts / updates
- Determining the primary keys, and conditions when values should be inserted/updated are also assummed without full confidence
- Overall, I'm confident that the approach / solution are conceptually mostly correct, but would be surprised if the solution is 100% correct and best-practice
