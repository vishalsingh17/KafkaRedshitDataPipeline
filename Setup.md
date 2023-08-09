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


- IPython

### Modular code
- Create virtualenv
- Install requirements `pip install -r requirements.txt`
- Run Code `python pyspark_redshift.py`
- Run Code `python pyspark_kafka.py`
- Check output for all the visualization
### IPython
Follow the instructions in the notebook `pyspark_redshift.ipynb`
Follow the instructions in the notebook `pyspark_kafka.ipynb`

 
