
# Upload the file into the s3 bucket Using rest API via API Gateway.

![bold s3](https://github.com/dharmaraj257/Upload-file-S3-bucket-Using-REST-API-via-API-Gateway/assets/100831265/03069f40-6922-42d2-80f5-4539eb609174)



### Step 1: Create a s3 Bucket

1. Go to s3 service and click Create Bucket.

2. Give a name, enable bucket versioning, and leave the same.

3. Click Create Bucket.


### Step 2: Create a role and attach policies.

1. Go to IAM service and click Create role.

2. Select Service API Gateway and click next.

3. Give the role name and click Create role.

4. To Attach policies click on created role

5. Click create policy, select s3 service, and add PutObject.

6. click Add ARN of s3 bucket, add bucket name select resource object name, and click add arn.

7. Next, Give a policy name


Step 3: Create an API Gateway 

1. Go to API gateway service, click Create API, select REST API, and click Build.

2. Select New API, Give a name API, and click Create API.

3. Create a resource bucket then filename.

4. Select filename, create method, select PUT, and click AWS service.

5. Select AWS region us-east-1, AWS service simple storage Service(s3), select HTTP method PUT, Action Type Use path override {bucket}/{filename}, Execution role Copy paste the created role arn.

6. Click the Create method.

7. Go to integration request and click edit.

8. In the URL path parameter, click Add path.

9. the first path gives the name bucket and method.request.path.bucket.

10. second path method.request.path.filename.

11. Go to API setting, In Binary Media Type, click add, add '/', and save changes.

12. Deploy API, Create a new stage, Give the name dev and click Deploy.

### Step 4: Using Postman upload the file in s3 bucket

1. copy the Invoke URL.

2. Go to the postman, select HTTP, select PUT method, and paste the URL.

3. Select Binary, click the select file, upload a text file, and click Send.

4. Check the Uploaded file in the S3 bucket.
