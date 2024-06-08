- Amazon EBS
	- Amazon Elastic Block Store
	- Persistent data storage / non-volatile storage
	- Replicated in two AZs; durability and high availability 
	- ![[Pasted image 20240604231754.png]]
	- EBS Snapshot
		- Baseline snapshot
		- Next snapshots: capture only the difference from baseline
		- Point-in-time snapshots
	- Encrypt at no additional cost
	- SSD (General Purpose vs Provisioned IOPS) vs HDD (Throughput optimized vs Cold)
	- Cost estimation: Volume (size), IOPS, Snapshots, Data transfer
	- `df -h`
	- `sudo mkfs -t ext3 /dev/sdf`
	- `sudo mkdir /mnt/data`
	- `mount /dev/sdf /mnt/data`
- Amazon S3
	- Amazon Simple Storage Service
	- Object store
	- Designed for 11 9s of durability
	- Storage classes
		- Standard
		- Intelligent-Tiering
		- Standard-Infrequent Access
		- One Zone-Infrequent Access
		- Glacier
		- Glacier Deep Archive
	- Buckets
		- Bucket path-style URL endpoint: need to access objects
		- Bucket virtual-hosted-style URL endpoint: using bucket for public website
- Amazon EFS
	- Amazon Elastic File System
	- Shared storage, supports Network File System
	- 5 steps for implementation
	- ![[Pasted image 20240605093005.png]]
- Amazon S3 Glacier
	- Data archiving service
	- Three terms: Archive, Vault, Vault access policy and Vault lock policy
	- Access (base on time to retrieve): Standard, Bulk, Expedited
	- Amazon S3 lifecycle policies: enable you to delete or move objects based on age
- ![[Pasted image 20240605201922.png]]
- ![[Pasted image 20240605202229.png]]
- 