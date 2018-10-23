# ansible-mastodon-amznlinux

Ansible construction script of mastodon instance

### AmazonLinux Version

* Amazon Linux 2018.03.0
* Amazon Lightsail ready

### Mastodon Version
* 2.5.0 ready

## SETUP

1. please rewrite group_vars file. `group_vars/production.yml`
2. let try `ansible-playbook -i localhost localhost.yml -vv`
3. start supervisord `nohup PATH=$PATH:/usr/local/bin:/usr/bin supervisord -n -c /etc/supervisord.conf >/dev/null 2>&1  &`

## Amazon S3 IAM Policy sampile

```
{
   "Version":"2012-10-17",
   "Statement":[
      {
         "Effect":"Allow",
         "Action":[
            "s3:ListAllMyBuckets"
         ],
         "Resource":"arn:aws:s3:::*"
      },
      {
         "Effect":"Allow",
         "Action":[
            "s3:ListBucket",
            "s3:GetBucketLocation"
         ],
         "Resource":"arn:aws:s3:::examplebucket"
      },
      {
         "Effect":"Allow",
         "Action":[
            "s3:PutObject",
            "s3:PutObjectAcl",
            "s3:GetObject",
            "s3:GetObjectAcl",
            "s3:DeleteObject"
         ],
         "Resource":"arn:aws:s3:::examplebucket/*"
      }
   ]
}
```
