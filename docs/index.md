## Fetch Insights from AWS CloudTrail Logs with Athena

**Introduction** 

Leveraging AWS Athena with CloudTrail logs is an impactful method to refine your insights of AWS service activity. For example, you can leverage queries to detect findings and further trace activity by attributes, like source IP address or user etc

Below are the steps we need to follow to implement this tutorial 

1. Configure S3 bucket

2. Configure Athena to persist result at right location

3. Link Cloudtrail with AWS Athena

4. Provision tables in AWS Athena

5. Retrieve insights from Athena table

    - Console Sign-in activity
    
    - AWS event errors
