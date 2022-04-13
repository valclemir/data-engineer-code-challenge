# Data Engineer Code Challenge
Code challenge for Data Engineer.

UMe is a startup dedicated to helping the population of classes C, D, and E in our society to have simple access to fair credit, fast and without hidden fees. We offer credit directly at the point of sale of partner small and medium retailers, who use our product as a payment option. Using our credit platform the retailer can sell its products while we assume all the credit operations-related transactions. These operations are related to handling payments, controlling default rates, and collection. 

As a Fucking Amazing Data Engineer, you will join our Data Platform team. You would work in a cross-functional team of skilled Engineers with backgrounds in Finance, Machine Learning, and Computer Science to develop our cutting-edge Insights tool. Based on the analysis of extensive supply- and demand-data sources, we plan for our clients to offer a better opportunity in credit. We analyze, visualize and simulate millions of data points using best-in-class technology.

Every time an action occurs in our system an event with a lot of information about it is generated. On the Data Platform we collect all events, and the data gives us insights, which we use to find out how we can best improve the score model and help people in their financial life. 

# Data Sources
The JSON files (payments.zip)[https://github.com/ScudraServicos/data-engineer-code-challenge/blob/main/payments.zip] and (originations.zip)[https://github.com/ScudraServicos/data-engineer-code-challenge/blob/main/originations.zip] files are a small sample of such a dataset. For further analysis (e.g. visualizations in a web app or simulations done by another microservice), the following requirements need to be met.

## Context and Definitions:

* Origination: Origination is a deal created between Ume and the customer, which means information on how much we borrow, how many installments were generated, and the values related to each installment.

* Payment: The payment represents that a specific installment was paid.

* Cohort: For the scope of this challenge, a cohort is the set of all clients that executed an origination in a given month. For example, the cohort of January is the set of all clients having an origination from 01 to 31 of January. 

# Everything begins in an ETL

We're a fintech, so...we breathe and live tech in here, with this being said we're data-driven. This means that everybody wants to see data, not only Data Analytics or Data Scientists, we mean all C levels, the Growth team, Marketing team, Engineers so they can create something unique that might impact how things run around here.

### The Task

With that being said, implement an ETL pipeline to process files and store them in a structured way, so everyone can get insights from it.

## Requirements
* SQL is the main language to analyze data. Thus, it must be accessed in a SQL way.
* Reliability is a really important thing, we can't lose data.
* Scalability is one of the foundations, we're growing, to infinity and even further. (Our test in here will run with much more data)
* Bonus: Run this solution with streaming sourced based on the files, an emulation is ok.

## Deliverable

* Feel free to use any language and framework you prefer. 
The only request is, the solution must be containerized in a docker image, everything ready to run. Run it should start reading the files and finish storing it as asked. Provide a readme explaining how to run it!

# Spark

In the credit risk literature, we define some rules based on some criteria to define if someone is what is called a bad payer or not. In this case, we'll be using two rules to define if someone is a bad payer or not. 

## The Task

We classify a customer as a bad payer if :

Given a cohort, after M months, the customer has an installment with more than D days of delay. We call this rule over-D-mob-M. Where we replace M and D with the proper values and mob stands for months of observation. 

Given a cohort, in a period of M months of observation, the customer delayed any installment with more than D days. We call this rule ever-D-mob-M.  Where we replace M and D with the proper values and mob stands for months of observation. 

* You will be given a set of origination events for a period of 6 months along with related payment events available on [Data Sources](#data-sources). Your task is to find the percentage of bad payers for all possible cohorts that fill the rules:
  * over-30-mob-1
  * over-30-mob-3
  * ever-30-mob-3

Moreover, with the percentage, you must provide the list of bad payers along with the installments that fill each rule. Save it as a parquet file partitioned by bad_payer = (true or false)

## Requirements
* Use the data provided (Bonus: use the data prepared on [Everything begins in an ETL](#everything-begins-in-an-etl))
* Use Apache Spark 
* Reliability is a really important thing, we can't lose data.
* Scalability is one of the foundations, we're growing, to infinity and even further. (Our test in here will run with much more data)

## Deliverable

* Feel free to use any language but do it with Apache Spark. 
The only request is, the solution must be containerized in a docker image, everything ready to run. Run it should start reading the files and finish storing it as asked. Provide a readme explaining how to run it!

# What about Governance and Privacy?

This is an important subject as we can't leave our customer information available to the world. So we need to make sure everything is under control.

## The Task

How would store metadata and build a catalog to secure it? The solution needs to take some points into consideration: 
  * Governance, who can access what
  * Privacy, how to store it in a private way 

## Deliverable

* Tell us how would you implement it.
  * You can sketch a solution with comments on frameworks and algorithms.
  * Feel free to find the best way to explain your ideas.
  * Bonus: You can implement it on the ETL task. Provide a readme explaining how to run it!


# Happy Coding!
## Remember to provide a readme for all the solutions!