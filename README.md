
**Overview**
This project uses AWS Lambda to scrape stock data from Yahoo Finance, format it into an HTML table, and upload it to an Amazon S3 bucket. The stock data includes the following attributes for each stock:
Symbol
Name
Price
Change
Percentage Change
The HTML file generated is formatted with inline CSS to ensure compatibility with email clients like Gmail.

**Files**
lambda_function.py: The main script that:

Scrapes stock data from Yahoo Finance.
Processes the data into a structured format.
Generates an HTML file with inline CSS for email compatibility.
Generates a Markdown version of the stock data.
Uploads both the HTML and Markdown files to an S3 bucket.
index.html (generated): An HTML file formatted with inline CSS to present stock data in a table. This file is uploaded to S3 and can be used in emails.

stock-results-1.md (generated): A Markdown file that also contains the scraped stock data.

**Prerequisites**
AWS Lambda: To run the script in the cloud.
Boto3: AWS SDK for Python.
BeautifulSoup4: For web scraping.
Requests: To make HTTP requests to Yahoo Finance.
**Setup**
Create AWS Lambda Function:

Set up an AWS Lambda function and attach it to an appropriate IAM role with permissions to access S3.
Upload lambda_function.py to Lambda.
Create S3 Bucket:

Create an S3 bucket (e.g., activemovers) to store the generated HTML and Markdown files.
Update the bucket variable in the script with your S3 bucket name.
Install Dependencies Locally:

If you wish to run the script locally for testing, install the required libraries:
bash
Copy
Edit
pip install boto3 requests beautifulsoup4
Modify Lambda Event (Optional):

If needed, adjust the Lambda event to trigger based on your use case, such as on a schedule or based on an API Gateway request.
