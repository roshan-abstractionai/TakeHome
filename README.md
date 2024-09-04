# Real-time Data Processing and Analysis System with AWS Integration

## Initial Tasks Breakdown

- Setup Kafka Zookeeper Producer Consumer locally. Start off with that by modifying the existing code
- Perform the PySpark analysis locally by chaining the data from the consumer
- Display the results as a log locally
- Create proper documentation to test the idea out and commit the code
(if time permits)
- Push the code to s3 instead of local pyspark
- Push the pyspark to an ec2 instance
- Run the ec2 instance using Lambda + API gateway 

## Flow Diagram

![Architecture Diagram](https://github.com/ashwin-sp/TakeHome/blob/76a492850000365bc3b81b39f1579e458f517565/flow_diagram.png)

## Setup and Running Instructions

- Install Kafka 
```
tar -xzf kafka_2.13-3.8.0.tgz
cd kafka_2.13-3.8.0
```
- Start Kafka and Zookeeper
```
bin/zookeeper-server-start.sh config/zookeeper.properties
bin/kafka-server-start.sh config/server.properties
```
- Create a topic 
```
bin/kafka-topics.sh --create --topic page_view --bootstrap-server localhost:9092
```
- Install the packages with the respective versions in a conda environment of your choice
```
pip install pyspark==3.4
pip install numpy==2.0
pip install pandas=2.2.2
```
- Download the source code
- Start the jupyter notebook and navigate to the folder containing the source code
- Run the KafkaProducer notebook first and then KafkaConsumer and see the results in the last cell of KafkaConsumer

## Design decisions and trade-offs

- Used hard coded topics
- Sent message object directly as json object to the consumer. Kept Producer as light weight as possible and did the parsing in a parallel thread in the Consumer
- Assumed product_view as event type to calculate top Product Views 
- Went with Data -> Kafka -> PySpark to prioritize evaluating the working idea

## Future considerations

- Push the Kafka to a cloud
- Should explore Kafka Groups and Partitions for data at scale
- Separate out the PySpark related code from the KafkaConsumer
- Should explore window functions for instances such as per hour calculations 
- Chain the output of KafkaConsumer to s3 by granting appropriate write permissions to s3 
- Push the PySpark local code as a script to a EC2 instance 
- Grant EC2 instance permission to access s3 bucket to perform inference on it
- Explore the possibility of CloudWatch Events to trigger the job
- Write results back to another s3 bucket
- Expose it as API by reading the result s3 bucket using lambda + API Gateway with proper CORS and rate limiting
- Create a budget to keep a track of the expenditure 


