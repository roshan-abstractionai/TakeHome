# Real-time Data Processing and Analysis System with AWS Integration
Test to see if I can make chagnes

## Background
You are tasked with designing and implementing a real-time data processing and analysis system for a large e-commerce platform. The platform generates a high volume of user activity data, including page views, clicks, purchases, and search queries. Your goal is to create a system that can ingest, process, and analyze this data in real-time to provide valuable insights to the business. The system will leverage AWS services for data storage and processing.

## Important Notes
Please don't spend more than 2-3 hours on the coding/development of this exercise.
It's okay if you don't finish everything – focus on demonstrating your thought process and approach to solving the problem
Its okay if the code isn't perfectly running. There will be a follow up session to review whats been done


## Requirements

1. Use Apache Kafka for initial data ingestion (optional - feel free to start with the sample data)
2. Use AWS S3 for data storage.
3. Implement PySpark jobs running on an EC2 instance.
4. Design a scalable and fault-tolerant architecture.
5. Implement real-time data processing pipelines.
6. Create at least one batch processing job for historical data analysis.
7. Provide a way to visualize or report on the processed data.

## Tasks

1. **Data Ingestion and Storage**:
   - Design a Kafka topic structure to handle the various types of user activity data.
   - Implement a simple data generator that simulates user activity and publishes it to Kafka.
   - Create a pipeline to move data from Kafka to an S3 bucket.

2. **EC2 and PySpark Setup**:
   - Set up an instance with PySpark installed.
   - Implement an API endpoint on the instance (Fast API) that triggers the PySpark job.

3. **Real-time Processing**:
   - Use PySpark to read data from the S3 bucket.
   - Implement at least two real-time analytics:
     a. Calculate and update the top 10 most viewed products in the last hour.
     b. Detect and flag potential fraud based on unusual user behavior patterns.

4. **Batch Processing**:
   - Implement a batch job that runs daily to calculate user cohort retention rates.

5. **Data Visualization**:
   - Choose an appropriate method to visualize or report on the processed data (you can mock this if time is limited).

6. **API and Job Triggering**:
   - Design and implement a simple API that allows triggering of the PySpark job on the EC2 instance.
   - Ensure the API is secure and can handle potential concurrent requests.

7. **Documentation**:
   - Provide a high-level architecture diagram of your solution, including AWS components.
   - Document your design decisions, including any trade-offs you considered.
   - Explain how your solution can scale to handle increased data volume.

## Deliverables

1. Source code for all components (data generator, Spark jobs, API endpoint, etc.).
2. Instructions to set up the AWS environment (EC2, S3) and deploy the solution.
3. README file with:
   - Setup and running instructions
   - Architecture diagram
   - Design decisions and trade-offs
   - Ideas for future improvements or optimizations
4. A simple script or instructions to demonstrate how to trigger the job via the API.

## Evaluation Criteria

- Overall architecture and system design, including effective use of AWS services
- Code quality and organization
- Effective use of PySpark features and S3 integration
- Design and implementation of the API endpoint
- Scalability and fault-tolerance considerations
- Clarity of documentation and explanations

