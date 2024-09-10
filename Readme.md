# AWS Cloud Cost Optimization - Identifying Stale Resources

## Identifying Stale EBS Snapshots

This Project, is to create a Lambda function that identifies EBS snapshots that are no longer associated with any active EC2 instance and deletes them to save on storage costs.

### Description:

The Lambda function fetches all EBS snapshots owned by the same account ('self') and also retrieves a list of active EC2 instances (running and stopped). For each snapshot, it checks if the associated volume (if exists) is not associated with any active instance. If it finds a stale snapshot, it deletes it, effectively optimizing storage costs.

## Permissions Requires For Lambda Function

Create Required Policises and Permissions attach to Lambda Function

```
Service(EC2) : DeleteSnapshot , DescribeSnapshots
```

```
Service(EC2-list) : DescribeInstances , DescribeVolumes
```

<img width="419" alt="Cost_Drawio" src="https://github.com/user-attachments/assets/c13e1d01-9755-4efd-9c52-27ab23349c9b">



