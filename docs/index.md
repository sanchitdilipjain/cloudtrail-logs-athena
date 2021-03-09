## Fetch Insights from AWS CloudTrail Logs with Athena

**Introduction** 

Leveraging AWS Athena with CloudTrail logs is an impactful method to refine your insights of AWS service activity. For example, you can leverage queries to detect findings and further trace activity by attributes, like source IP address or user etc

Below are the steps we need to follow to implement this tutorial 

1. Configure S3 bucket
    
    - Navigate to S3 console
      
      <img src="images/image1.png" class="inline"/> 
           
    - Select Create bucket button
      
      <img src="images/image2.png" class="inline"/>
    
    - Enter a Bucket name which globally unqiue
      
      <img src="images/image3.png" class="inline"/> 
      
    - Leave rest else as default and click Create bucket

      <img src="images/image4.png" class="inline"/>
      
      <img src="images/image5.png" class="inline"/>
    
    - Verify that bucket is created successfully 
      
      <img src="images/image6.png" class="inline"/>

2. Configure Athena to persist result at right location

    - Navigate to S3 console

      <img src="images/image7.png" class="inline"/> 

    - Select on Get Started

      <img src="images/image8.png" class="inline"/> 

    - Select on Settings at top right corner of the screen

      <img src="images/image9.png" class="inline"/> 

    - Enter Query result location with your S3 bucket and select Save button in the bottom

      <img src="images/image10.png" class="inline"/> 

3. Link Cloudtrail with AWS Athena

    - Navigate to S3 console

      <img src="images/image11.png" class="inline"/> 

    - Select Create Athena Table

      <img src="images/image12.png" class="inline"/> 

    - Choose Storage location from the dropdown where Cloudtrail logs are persisted and Click on Create table 

      <img src="images/image13.png" class="inline"/> 

4. Switch back to AWS Athena console

    - On the left, choose default Database and you will see the Athena Table Name

      <img src="images/image14.png" class="inline"/> 

    - Execute a Select query with limit rows to verify the configuration 

      <img src="images/image15.png" class="inline"/>
  
5. Retrieve insights from Athena table

    - AWS Sign-in activity: The below query provides user-level details with respect to the AWS console login event
 
           SELECT *
            FROM cloudtrail_cloudtrail_logs
            WHERE eventname = 'ConsoleLogin'
    
   
