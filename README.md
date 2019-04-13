# Papers4DataAchitect
## Background
There are so many kinds of ***distributed data store systems*** , ***distributed compute systems***, ***distributed machine learning system*** in DT times.

- As a application engineer, you may use RDBMS,NoSQL even NewSQL to store and manage data.

-  As a data enginner, you may 

  - collect data first
    - extract data from app's log file
    - capture data chang in RDBMS or NoSQL database,
    - crawl data from various web sites
    - pull data from third party data vendor through web service api
    - massive time sequence data from IOT frontend or some sensor  such as car-net or monitor-camera with AI enhancement.

  - clean and transform data next
    - use some ETL utility or run-time stream process system such as  flink, kafka.
  - analyze and training data at last
    -  analyzed in spark/SQL on hadoop/OLAP datawarehouse,  generate data report and visual the result use some tools such as tableau.
    - training machine learning models in a distributed machine learning system such as spark ML-Lib,  Angel. These model will make some adervtise CTR inference or user recommendation.

## Purpose
It is a key ability  to work efficently with the different utility for big data/ML pipeline. However, various tools for big data and machine learning are more complicated and more complex. These tools is neither mature as traditional RDBMS nor simple as local algorithm library sucha as sk-learn . Sometimes digging deep into the implemention details of a distributed data store/process/training system may be hard and unnecessary. Nevertheless,  understanding some common sense of the software stack will be a great help. 

 Different  system do have some common sense and design patern. It it a good idea to read the original paper which describles the background ,key algorithm,author's consideration. For a data architect or algorithm engineer,  reading these paper may be a greate help.

This repository wll collect and classify these papers as a user guide for data/algorithm enginner/architectur.

## How to read
A short comment w available as user guide for every paper. The comment consist of background description, abstraction, and contrast between similar systems.

**Contents**

- **[Online Analysis Process](./OLAP)**
- **[New SQL DB](./newSQL)**
- **[Run-time Streaming Compute](./runtimeStreamCompute)**
- [**Graph Compute**](./GraphCompute)
- **[Distributed Machine Learning Paradigm](./distributedML)**
- **[LinkedIn Big Data Stack](./linkedin)**

