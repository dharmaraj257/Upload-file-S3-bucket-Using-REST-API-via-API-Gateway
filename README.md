
# Upload file into s3 bucket Using rest api via API Gateway.

A brief description of what this project does and who it's for

### Step 1: Create a s3 Bucket

1.Go to s3 service and click create bucket.

2.Give name, enable bucket versioning and leave the same.

3.Click create bucket.


### Step 2: Create a role and attach policies.

1.Go to IAM service and click create role.

2.Select Service API Gateway and click next.

3.Give role name and click create role.

4.To Attach policies click to created role

5.Click create policy,select s3 service and add PutObject.

6.click Add ARN of s3 bucket, add bucket name select resource object name click add arn.

7.Next, Give policy name


Step 3: Create a API Gateway 

1.Go to api gateway service,Click create api,select REST API and click Build.

2.Select New API, Give a name api and click create api.

3.Create a resource bucket then filename.

4.Selct filename,create method, select PUT, click AWS service.

5.Select AWS region us-east-1, AWS service simple storage Service(s3),select HTTP method PUT, Action Type Use path override {bucket}/{filename}, Execution role Copy paste the created role arn.

6.Click create method.

7.Go to integration request and click edit.

8.In URL path parameter,click add path.

9.first path give name bucket and method.request.path.bucket.

10.second path method.request.path.filename.

11.Go to API setting,In Binary Media Type, click add, add '/' and save changes.

12.Deploy API, Create a new stage,Give name dev and click Deploy.

### Step 4: Using postman upload file in s3 bucket

1.copy the Invoke URL.
2.Go to postman, select HTTP, selct PUT method and paste the url.
3.Select Binary and click select file and upload text file and click send.
4.Check Uploaded file in S3 bucket.
