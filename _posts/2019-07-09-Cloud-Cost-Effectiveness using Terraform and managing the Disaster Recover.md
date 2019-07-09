
One of the ideal thought for any organisations is "Do we need Disaster Recover DataCenter/Region ? " . Answer is obviously YES.  
Next question will be  "Do we need to spend similar pricing for Disaster Recovery also ?"  For now,  answer is YES.

is their anyway we can reduce the Disaster Recovery Data center price? (without sacrificing the performance, Non functional requirements )

Here are my thoughts from eagle view.
![enter image description here](https://github.com/cnuonline/cnuonline.github.io/raw/master/assets/Zone%20wise%20deployment%20and%20Data%20center.png)
Diagram showing the Deployment is happening away from the hosted regions. Neither of Production or DR Region

**Assumptions**: Dont prefer the Custom hosting vendor stack of any hosting vendor , machines, networking. Try to have control on your own VM's, Routers, networking, storages. ( Example : AWS EC2 machine image, Dynamo DB, Route 53..) Instead take CentOS/Ubuntu , Apache/NGINX/HA proxy, mysql/mongodb ...

1. How do we define the app infrastructure agnostic to  hosting  centers? Picking the market ready opensource versions which can be deployed on any datacenter

2. What could be be stack? Simple VM's or EBS ? Prefer CentOS /Ubuntu vm image 

3. HA proxy/ NGINX or Route53 ? Prefer NGINX

4. Define your deployment models away from your Hosting zones.  This is to make sure any Firewall gap's , security gaps , DR critical times also, you are least worried.

5. Orchestrate deployment models away from the zone. Pick a right IaaC tool (Infrastructure as a code) which could be Ansible C or Terraform which can have full control on every operation which we perform.

6. Use F5 for serving both the zones. Have F5 or any other load balancer to automatically listen the heartbeat and availability of regions or apps

