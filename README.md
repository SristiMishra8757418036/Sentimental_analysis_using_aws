# Sentimental_analysis_using_aws
Sentiment analysis is the process of analyzing the sentiments in a piece of text with the help of various algorithms. Using sentiment analysis, we can analyze various emotions, particularly if it is positive, neutral, or negative. This has enabled the development of intelligent applications with a better understanding of the text received.   
we will learn how to analyze the sentiments from a piece of text using AWS services like Amazon Comprehend, AWS IAM, AWS Lambda, and Amazon S3. So before you get started, make sure you have access to all these services. You can access all of these services through your management console.

Let’s get started!

IAM Permission for Amazon Comprehend
Using your management console, select the IAM service. Once you land on the IAM dashboard, on the left side, you will see Access Management. In that, select Roles to add an IAM role to give various permissions. Click on Create role button. 

As we will be using AWS Lambda, we need to select Lambda and click on Permissions (right-hand side below) to add various permissions to our role.
Select ComprehendFullAccess and AWSLambdaExecute.
You can filter out the permissions, and then once selected, click next!
Give an appropriate name and description to your role, and once you select Create role, a new role gets created, which can be accessed anytime from your existing list of roles from the IAM Management Console. 
Once the role is created, we will move to the S3 Management Console. Create a text document on your local device and then use that to analyze the docs' sentiments. For that, first, create a bucket. Make sure you are keeping the bucket as public to test with the Lambda function for text analysis.
Once it is created, then upload a text document like that, and then the S3 bucket will look like this after uploading various documents. Max size of the file needs to be lesser than 5000 bytes.
The last and final step is to create a Lambda function to analyze the text document we uploaded in the S3 bucket. 
Here, I have created the function sentiment_lambda. We will use Python 3.8 for our runtime. The existing role myrole11111 we created earlier will be used with the Lambda function.
Through the Lambda Management Console, we can access the created function, and then we will click on that to write a function code for performing our task of sentiment analysis using Python 3.8. Here, we will enter the name of the S3 bucket we created, and the key will be the name of the file to be analyzed (uploaded in the same bucket).
    Save your function code and then test your code to see the results with the analysis of the text you directed through your bucket and key.
    Once you test your function code, it will give the results for your text. The section of results shows the logging calls in the code. They correspond to a single row within the CloudWatch log group with this 
    Lambda function
