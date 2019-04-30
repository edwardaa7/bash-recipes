### s3ql systemd script for Bitnami (Debian)

I'm using this with Bitnami Wordpress (Debian) distribution to mount an S3 bucket into the wordpress uploads folder using [s3ql](https://github.com/s3ql/s3ql).


This is a systemd script to automate the mount / unmounting of the S3 bucket before Bitnami starts up.


Installation steps:
1. Copy the file etc/init.d/s3ql to your Bitnami deployed environment at /etc/init.d/s3ql


2. Set up the authinfo2 file in /root/.s3ql/authinfo2. The content of the file typically looks like this:
```
[s3]
storage-url: s3://your-bucket-name-here
backend-login: YOUR-AWS-ACCESS-KEY-ID
backend-password: YOUR-AWS-SECRET-ACCESS-KEY
```


3. Edit and onfigure the BUCKET and MOUNTPOINT variables in /etc/init.d/s3ql


4. Copy the file etc/systemd/system/s3ql.service to /etc/systemd/system/s3ql.service


5. Enable the service
```
systemctl enable s3ql.service
```
