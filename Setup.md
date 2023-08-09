1. Run the docker-compose
```
docker compose up
```

2. Get into bash shell of different containers
```
docker exec -it broker bash
```
3. Create a kafka topic
```
kafka-topics --create --topic airline-topic --bootstrap-server localhost:9092 --replication-factor 1
```

4. List all kafka topics
```
kafka-topics --list --bootstrap-server localhost:9092
```

5. Create a virtual environment
```
conda create -n env python==3.9 -y
```

6. Activate the environment
```
conda activate env
```

7. Install the required packages
```
pip install - r requirements.txt
```

8. Run the pyspark_kafka notebook in notebook directory

9. Consumer data sets
```
kafka-console-consumer --topic airline-topic --bootstrap-server localhost:9092 --from-beginning
```

10. Store data in new topic
```
kafka-console-consumer --topic airline-shink --bootstrap-server localhost:9092 --from-beginning
```

11. Setup Redshift

[Redshift Setup](https://github.com/vishalsingh17/KinesisRedshiftDataPipeline/blob/main/AWS%20SET%20UP/5%20--%20AWS%20redshift%20Creation.docx)

12. Create DB in Redshift
```sql
Create database test_data
```

13. Create table in Redshift
```sql
CREATE TABLE emp(

   emp_id int, 

   emp_name varchar (255),

   emp_city varchar (255),

   emp_sal int,

   emp_phone int

   )

```

14. View the table
```sql
select * from emp;
```

15. Insert Data into table
```sql
INSERT INTO emp (emp_id, emp_name, emp_city,

   emp_phone, emp_sal) VALUES(1,'ram', 'Hyderabad', 7348, 50000);



INSERT INTO emp (emp_id, emp_name, emp_city,

   emp_phone, emp_sal) VALUES(2,'robin', 'Hyderabad', 9843, 40000);



INSERT INTO emp (emp_id, emp_name, emp_city,

   emp_phone, emp_sal) VALUES(3,'amit', 'Hyderabad', 9848, 25000);



INSERT INTO emp (emp_id, emp_name, emp_city,

   emp_phone, emp_sal) VALUES(4,'nikhil', 'Hyderabad', 9848, 45000);



INSERT INTO emp (emp_id, emp_name, emp_city,

   emp_phone, emp_sal) VALUES(5,'uday', 'Hyderabad', 9848, 35000);



INSERT INTO emp (emp_id, emp_name, emp_city,

   emp_phone, emp_sal) VALUES(6,'deepak', 'Hyderabad', 9038, 20000);
```

16. View the table
```sql
SELECT * FROM emp;
```

#  Spark Integration with  Redshift and Kafka
Spark can read and write data from anywhere.
# Why we need Integration
To fast data processing.

    
# Extract , Transformation and Load 
To create data pipline we need ETL .


# PySpark Integration with Redshift.
Read write data from Redshift

#Note- 
- need redshift jdbc jar file
- need aws credentials : AccessKey and AccessSecretKey



# PySpark Integration with Kafka.
Data extraction using Kafka
#Requirements: AWS Cloud

- Amazon Simple Storage Service (Amazon S3, Redshift)
# Code Description
    File Name : pyspark_redshift.ipynb, pyspark_kafka.ipynb, pyspark_redshift.py and pyspark_kafka.py
    DataSets : airlines1.csv
    Jar files : redshift-jdbc42-2.0.0.4.jar
    File Description : Integration of pyspark with Redshift and Kafka.
    

#NOTE :- use findspark library when executing python script

 - import findspark
 - findspark.init()

## Steps to Run
There are two ways to execute the end to end flow.
 - Command Prompt => python script
 - spark_path spark-submit file_path
 - spark_path => <path_to_spark>>
 - file_path => <path_to_file>
 - Data file path is same as script file path

eg. <C:\Users\admin\Desktop\spark\bin>spark-submit C:\Users\admin\Desktop\Integration\pyspark_redshift.py>

### Modular code
- Create virtualenv
- Install requirements `pip install -r requirements.txt`
- Run Code `python pyspark_redshift.py`
- Run Code `python pyspark_kafka.py`
- Check output for all the visualization

### IPython
Follow the instructions in the notebook `pyspark_redshift.ipynb`
Follow the instructions in the notebook `pyspark_kafka.ipynb`

