# AWS Cloud Cost Saving process and  Challenges. 

If you are spending 4 digit dollars on every month, then this information is more relevant.  Any complex application stack which has Data tier, App Tier, Content tier,  Network & Load Balancer Tier and Monitoring Tier.
Let's go through the quick questions .

## a. Does the app is being developed through Multi Cloud (Hybrid) approach ?
Formulate the basic checklist questions
 - How does the app/product stack was being deployed ?
 - How does the traffic routing through DNS, LB & App flow? 
 - How does the monitoring is being configured ?
 - Peak & offpeak hours ?
 - Devops pipeline and Continuous provisioning model?
 - Security checkpoints & tools ?
 - Disaster Recover mechanism ?
 - Backup's duration ?
  Formulate the cost associated to it

## b. Does it require 100% instance availability ? Day time & Night time also ?

Choose the right sizing of EC2 instance and what it requires for the app.
**Steady state:** The load remains constant over time, making forecasting simple. Consider using Reserved Instances. • Variable, but **predictable**: The load changes on a predictable schedule. Consider using 
**Auto Scaling**. • Dev/test/production: Development, testing, and production environments can usually be turned of outside of work hours. 
 **Temporary**: Temporary workloads that have fexible start times and can be interrupted are good candidates for Spot Instances.

## c. Does the stack requires to run specific zone ? Can it be run on the lower cost zones ?

- AUTOMATING TIMEBASED ELASTICITY  
- Amazon EC2 Scheduler &  Amazon EC2 API tools -->Programmatically terminates the instances.
- AWS Lambda --> Threshold based events to trigger the start/stop instances
- AWS DataPipeline --> Manage through AWS CLI commands for scheduling.
 - Amazon CloudWatch --> stops the unused or underutilized EC2 instances 
 
 # AUTOMATING VOLUMEBASED ELASTICITY

 - Auto Scaling: This is a straight forward. Automatically increases the
   number of Amazon EC2 instances during demand spikes   Application
 -  Auto Scaling: Automatically scales resources for other AWS services
  - Amazon ECS: Can scale services automatically in response to
  - CloudWatch alarms.  Amazon EC2 Spot Fleets: Launches or terminate
   instances according to scaling policies. 
   -Amazon EMR clusters (Elastic MapReduce): Scales out and scales in core and task nodes in a
   cluster.  
   -AppStream 2.0 fleets: Adjusts the size of a fleet
   automatically based on utilization metrics, and optimizes the number
   of running instances to match demand. 
   -Amazon DynamoDB: Dynamically
   adjusts provisioned throughput capacity in response to actual traffic
   patterns.

# OnDemand - Reserved - Spot instances

| On-Demand | Reserved  | Spot Instances |
|--|--|--|
|$5,000/mo  | $3,000/mo  **($2,000/mo)** |   $1,000/mo  **($4,000/mo)** |
|$60,000/mo  | $36,000/mo  **($24,000/mo)** |   $12,000/mo  **($48,000/mo)** |

**Storage optimization**
- S3 - Redefine the purge policies & Retention policies , migrate to the cheaper tier.
- EBS -(Elastic block storage) -->Resize the snapshot and remove the unwanted snapshots

**Change the culture:**
- Make use of tagging feature for every resource for better understanding in elastic search and also the cost explorer
- Not everytime the low cost model is successful. Tradeoffs between speed-to-market and upfront cost optimization are consciously chosen.
- Costs are clearly allocated using linked accounts and tags.
AWS is going very aggressively ,  frequent reviews on every quarter will help on cost optimization and correct way of doing with AWS.

