# S3 Multi-Region Access points

## Create S3 buckets in desired regions and creating Multi-Region Access points.

- Create a bucket with region as Canada & Sydney and an unique name. Enable versioning in both the buckets.

![Fig 1](S3%20Multi-Region%20Access%20points%2099fc0ff11311489e8e94db70c46c5a17/Untitled.png)

Fig 1

- Create Multi-Region Access Point

![Fig 2](S3%20Multi-Region%20Access%20points%2099fc0ff11311489e8e94db70c46c5a17/Untitled%201.png)

Fig 2

![Fig 3](S3%20Multi-Region%20Access%20points%2099fc0ff11311489e8e94db70c46c5a17/Untitled%202.png)

Fig 3

- Once the multi-region access point is created, select create replication rule.

![Fig 4 Template can be chosen based on the application.](S3%20Multi-Region%20Access%20points%2099fc0ff11311489e8e94db70c46c5a17/Untitled%203.png)

Fig 4 Template can be chosen based on the application.

- Make sure the scope is applied to all the objects in the bucket

![Fig 5](S3%20Multi-Region%20Access%20points%2099fc0ff11311489e8e94db70c46c5a17/Untitled%204.png)

Fig 5

![Fig 6](S3%20Multi-Region%20Access%20points%2099fc0ff11311489e8e94db70c46c5a17/Untitled%205.png)

Fig 6

## Testing the Multi-Region Access points

```bash
dd if=/dev/urandom of=test3.file bs=1M count=10
aws s3 cp test3.file s3://arn:aws:s3::634211996823:accesspoint/mir59qwhf769m.mrap
```

![Fig 7](S3%20Multi-Region%20Access%20points%2099fc0ff11311489e8e94db70c46c5a17/Untitled%206.png)

Fig 7

![Fig 8](S3%20Multi-Region%20Access%20points%2099fc0ff11311489e8e94db70c46c5a17/Untitled%207.png)

Fig 8

From the above 2 snaps we can understand that the file is transfer first to the Sydney region and then replicated in the Canada region.