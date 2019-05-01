# CMPE-266-Project: 
    Video Streaming using Kinesis and facial recognition using AWS Rekognition

# University Name: 
    San Jose State University http://www.sjsu.edu/ 

# Course: 
    CMPE 266 Big Data Engineering and Analytics http://info.sjsu.edu/web-dbgen/catalog/courses/CMPE266.html

# Professor: 
    Sanjay Garje https://www.linkedin.com/in/sanjaygarje/

# Student: 
    Aastha Kumar (https://www.linkedin.com/in/aastha-kumar-57417a9b/)

    Ritika Chadha

    Anjana Pradeep https://www.linkedin.com/in/anjana-p/

    Spandana Pandala

    Prasanna Kona
  
# Project Introduction: 
    We plan to use AWS Recognition and Amazon Kinesis Streams to perform the facial analysis on a live video stream. 
    The idea is to define a few faces as known faces and use AWS SNS service to send an alert whenever any known face
    appears in the video. This application can be easily extended to build an auto unlock door service at home. 
    The door is unlocked only when the known face appears in front of the front-door camera. 

# Features List
    1. Capture the live video stream from the webcam.
    2. Process the captured video stream using AWS Kinesis.
    3. Train AWS Recognition algorithm with known faces. 
    4. Analyze the video to detect known faces.
    5. Send notifications whenever the known faces appear in video.

# Demo Screenshots 
    Whenever it finds a known face in video, it sends the notification with the Name of the person recognized and the link to S3 bucket containing the image of the person. Clicking on that s3 link, one can see the image of the person matched in the video.

![Alt text](/Notification.png?raw=true "Notification Email")

# Pre-requisites Set Up 
    MAC OS steps 
    1. AWS account - You need to have an aws account to try out this project.
    2. Create a user using AWS IAM service and assign following permissions to the user
       a) AmazonKinesisFullAccess
       b) AmazonKinesisVideoStreamsFullAccess
       c) AWSLambdaKinesisExecutionRole
       d) AmazonS3FullAccess
       e) AmazonKinesisAnalyticsFullAccess
       f) CloudWatchFullAccess
     Then navigate to the security credentials tab and generate the access and secret key for future use.
    3. Install aws cli - Follow instructions given on https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-install.html
       Sometimes when starting the aws cli, it complains that groff is missing. Install groff using following command - 
       brew install groff gs
    4. Install following tools (Pre-requisites for step 5)
       cmake - brew install cmake
       autoconf - brew install autoconf
       bison - brew install bison
       pkg-config - brew install pkg-config
       install java jdk - https://docs.oracle.com/javase/10/install/installation-jdk-and-jre-macos.htm#JSJIG-GUID-F575EB4A-70D3-4AB4-A20E-DBE95171AB5F
    5. Clone AWS SDK for connecting your laptops webcam to AWS Kinesis from following link
    https://github.com/awslabs/amazon-kinesis-video-streams-producer-sdk-cpp#building-from-source
    From terminal - Navigate to the folder, then go to kinesis-video-native-build folder and then run ./install-script
    5. Create a bucket in amazon s3 (name - cmpe-266-project) and upload the images of people you want to give the access.
    6. Open aws cli and create a face collection that will be used by AWS Rekognition (We named it cmpe266VideoRek) 
    aws rekognition create-collection --collection-id cmpe266VideoRek --region us-west-2
    7. Use AWS rekognition to create face bounds for the images uploaded to S3. You need to run the following command for each of the image uploaded to S3 bucket (Replace "cmpe-266-project" with your S3 bucket name, "Aastha.jpeg" - with the image name, "cmpe266VideoRek" - collection name created in step 6, and "Aastha" with the name of person in image.
    aws rekognition index-faces --image '{"S3Object":{"Bucket":"cmpe-266-project","Name":"Aastha.jpeg"}}' --collection-id "cmpe266VideoRek" --detection-attributes "ALL" --external-image-id "Aastha" --region us-west-2
    8. Create a simple notification service using aws sns service - Follow the steps on the following link to create a topic 
    https://docs.aws.amazon.com/sns/latest/dg/sns-getting-started.html
    After you subscribe to this service, you will receive an email to confirm subscription
    
    


    
