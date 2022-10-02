## Mandatory assignments

**Assignment 1:**

Three line sample of the S3 access logs for your bucket: 
```
708f330e7fac3ae54d21c37ba985c4f0b201eb37ab063e6d7e1752efb02df91e week2-homework [30/Sep/2022:19:56:43 +0000] 80.62.116.254 708f330e7fac3ae54d21c37ba985c4f0b201eb37ab063e6d7e1752efb02df91e 413F9935K01RMAKN REST.GET.PUBLIC_ACCESS_BLOCK - "GET /week2-homework?publicAccessBlock= HTTP/1.1" 200 - 330 - 19 - "-" "S3Console/0.4, aws-internal/3 aws-sdk-java/1.11.1030 Linux/5.4.207-126.363.amzn2int.x86_64 OpenJDK_64-Bit_Server_VM/25.302-b08 java/1.8.0_302 vendor/Oracle_Corporation cfg/retry-mode/standard" - JVf8NExKByV7x1c0vCAhmrek//WjFc87f3E7Q+KbigtyrDpPHkjiYyqEkDMnwe0oRNcoDMc3XsM= SigV4 ECDHE-RSA-AES128-GCM-SHA256 AuthHeader s3.amazonaws.com TLSv1.2 -
```

How would you calculate total impressions based on the S3 access logs format? 
```
We can use that logs in a database. After that we can get informations or counts with this way.
Here is an example:
SELECT Bucket, Requester, RemoteIP, Key, HTTPStatus, ErrorCode, RequestDateTime
FROM s3_access_logs_db
WHERE Operation='REST.GET.OBJECT' AND
parse_datetime(RequestDateTime,'dd/MMM/yyyy:HH:mm:ss Z') 
BETWEEN parse_datetime('2022-09-30:22:42:42','yyyy-MM-dd:HH:mm:ss')
AND 
parse_datetime('2019-07-02:00:42:42','yyyy-MM-dd:HH:mm:ss') 
Source link: https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-s3-access-logs-to-identify-requests.html
```

**Assignment 2:**

1. The URL of the public API: `https://g7qyx992d9.execute-api.us-east-1.amazonaws.com/Prod/products`
2. The URL of the website using the API: `https://week2-homework.s3.us-east-1.amazonaws.com/index.html`
3. Screenshot of the updated service map: ![image](https://user-images.githubusercontent.com/67079251/193426357-3bc02c04-a639-4cb7-9c01-91722915c7b1.png)
4. Which service has the highest latency: `Api Gateway has highest latency with 0.6 t/min`

**Optional assignment**

1. Screenshot of the layer in the AWS console, clearly showing the ARN: 
![image](https://user-images.githubusercontent.com/67079251/193427442-13f6a20a-c4bf-4c24-a76a-9fb06e356235.png)
2. Screenshot of the lambda function, clearly showing that it is now using the created layer: 
![image](https://user-images.githubusercontent.com/67079251/193427567-a8a2ec9a-b9bb-49b2-b0b1-c0034cb19621.png)
![image](https://user-images.githubusercontent.com/67079251/193427586-8cef96a9-26b0-44b7-b7e2-653db25cd03f.png)