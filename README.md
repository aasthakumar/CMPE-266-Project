# CMPE-266-Project 

Video Streaming using Kinesis and facial recognition using AWS Rekognition

# University Name: 
  San Jose State University http://www.sjsu.edu/ 

# Course: 
  CMPE 266 Big Data Engineering and Analytics http://info.sjsu.edu/web-dbgen/catalog/courses/CMPE266.html

# Professor: 
Sanjay Garje https://www.linkedin.com/in/sanjaygarje/

# Student: 
  Aastha Kumar (https://www.linkedin.com/in/aastha-kumar-57417a9b/), 
  
  Ritika Chadha,
  
  Anjana Pradeep https://www.linkedin.com/in/anjana-p/, 
  
  Spandana Pandala, 
  
  Prasanna Kona
  
# Project Introduction 
We plan to use AWS Recognition and Amazon Kinesis Streams to perform the facial analysis on a live video stream. The idea is to define a few faces as known faces and use AWS SNS service to send an alert whenever any known face appears in the video. This application can be easily extended to build an auto unlock door service at home. The door is unlocked only when the known face appears in front of the front-door camera. 

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
  Here includes bullet point list of resources one need to configure in their cloud account. (E.g. For AWS: S3 buckets, EMR   etc.)
  List of required software to download locally (E.g. Spring, JDK, Eclipse IDE etc.)
  Local configuration
  How to set up and kick-off project from developer sandbox?
  Here include quick steps on how to compile and run your project on local machine (whichever you used, Mac or Windows either one).
