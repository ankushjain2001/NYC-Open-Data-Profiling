# The Generic and Semantic Profiling of Big Datasets

### [View PDF of draft](https://github.com/theodorehadges/ACM_data_profiling_paper/blob/master/project_files/generic_and_semantic_profiling_of_big_datasets.pdf)


<hr>

We call ourselves **CreaTAK**  
**T** is for [Theodore](https://github.com/theodorehadges)  
**A** is for [Ankush](https://github.com/ankushjain2001)  
**K** is for [Kat](https://github.com/ruinanzhang)  
...and we all like to **create** stuff.


In this study, we ran [Apache Spark](https://spark.apache.org/) over 
[NYU’s 48-node Hadoop cluster](https://wikis.nyu.edu/display/NYUHPC/Clusters+-+Dumbo), running [Cloudera CDH 5.15.0](https://www.cloudera.com/products/open-source/apache-hadoop/key-cdh-components.html), to generically and semantically profile 1159 datasets from [NYC Open Data](https://opendata.cityofnewyork.us/). We refer to these two profiling methods as Task 1 and Task 2, respectively.

Of the 1159 files we profiled in Task 1, we found 11674 integer columns, 13646 text
columns, 1137 date/time columns, and 4527 real number columns. For Task 2, we
analyzed 260 columns and we were able to identify the semantic types for 210 columns
with a precision of 72.40%.

<hr>

### Instructions

- Log into NYU's [DUMBO](https://wikis.nyu.edu/display/NYUHPC/Clusters+-+Dumbo).
- Load the correct versions of Python and Spark:  
  - `module load python/gnu/3.6.5`  
  - `module load spark/2.4.0`  

#### Task 1: Generic Profiling
- Navigate to `task1/src/`
- Type the following to run:
  - `spark-submit --conf spark.pyspark.python=$PYSPARK_PYTHON task1.py`


#### Task 2: Generic Profiling
- Navigate to `task2/src/`
- Type the following to run:
  - `spark-submit --conf spark.pyspark.python=$PYSPARK_PYTHON task2.py`
- Use **task2_md.py** to execute with 'en_web_core_md' NLP model. This model was used to produce the final results.
- This model is not available on dumbo by default. Use the following command to install the package.
> python -m spacy download en_core_web_md


