Storage
=======

- Must support Asia-Pacific, US, and Europe
- Customers can upload documents and images
- Manipulation is performed to the uploaded data
- Need to migrate from a server hosting company


Current Specs
-------------
- Microsoft SQL Server Std Edition databases Windows 2016 Base
- 8 CPUs
- 32-GB memory
- 5-TB storage
- DBAs access and manage the database


Facts: EBS
----------
- EBS is automatically replicated within its availability zone.
- Attachable block-level storage, good for running a database on an EC2
- Snapshots for disaster recovery
- Can change dynamically
- Highly available, highly reliable
- Have a scope of availability zone


Facts: S3
---------
- Object storage (in buckets)
- Managed cloud storage (11 9s durability)
- Single object is limited to 5 TB
- Can be images/video/logs
- Can be encrypted
- Can set up notifications to trigger processes (lambda/etc)
- Standard-Infrequent for logs maybe? (one zone-infrequent cheaper, but one AZ)
- Standard-Infrequent for long term storage
- Glacier deep archive, good for healthcare (accessed 1-2 times a year)
- Glacier deep archive stored across at least 3 AZs
- Buckets have access log
- Scales
- Access via console, cli, sdk
- Store a virtually unlimited amount of data

Facts: RDS
----------
- managed gives access control, but requires less setup
- managed provides scaling automatically
- Supports Microsoft SQL Server
- Can run in VPC, typically in a private subnet
- Multi-AZ deployment, automatically generates a standby copy in another AZ within the same VPC
- Automatically uses standby in event of an error
- Supports read replicas, if configured
- Can have reserved instances for 1yr or 3yr team


Conclusion
----------
- Managed RDS seems best
- AWS Database Migration Service provides an easy, self-service migration between homogeneous database types
- Can setup development/test instances
- DB should exist in a private subnet
- S3 buckets have an access log (can use CloudTrail for general logs)
- Can use multi-az deployment
- Can choose to use older version of MS SQL Server if so choose
- Multi-AZ DB instance vs Cluster (cluster can be used later, provides read access to standby DB instance)
- Can enable automatic backups
