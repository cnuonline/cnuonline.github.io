
Picking right tool of Layer 7 & Layer 4 network tools (load balancer, traffic routes)  is challenging especially choosing the opensource, cloud agnostic tech stack . want to share the knowledge on selecting the tools with certain criteria
Criteria:
1. List down the various interaction points - mobile, web, api, intranet traffic, external vendors/parties
2. List down the applications and source of the traffic
3. List down the apps/source which requires strict validation, firewall, token validation, trusted sources(intranet calls) 
Something which can be visualized as a matrix . (Ideally , we require cube kind of a model to represent)

|  |  ReactJS| Functional API cluster1 |Functional API cluster1|Mobile|External Vendor| Intranet App|
|--|--|--|--|--|--|--|
| Oauth | Yes |Optional| Optional |Yes|No  |No|
| Web App Firewall| Yes |Optional| Optional |Yes|No  |No|
| Traffic Route| Yes |Optional| Optional |Yes|No  |No|
| UnAuthorized Check (Token validate) | Yes |Optional| Optional |Yes|No  |No|


Possible tools which has opensource & enterprise version support.
|  | Nginx |Apache|HA Proxy| API Gateway|Azure Frontdoor|AWS CloudFront|
|--|--|--|--|--|--|--|
|Opensource & Free| Yes |Yes |Yes |Yes | Yes  |Yes  |
|Enterprise Support| Yes |Yes |Yes |Yes | Yes  |Yes  |
|Oauth support| Yes |Yes |Yes |Yes | Yes  |Yes  |
|Load Balancer| Yes |Yes |Yes |Yes | Yes  |Yes  |
|Traffic rules| Yes |Yes |Yes |Yes | Yes  |Yes  |
|Reverse proxy support| Yes |Yes |Yes |Yes | Yes  |Yes  |
Take a decision based on your budget or already existing relationship with the product tools.


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExMDQxMTQ1MDldfQ==
-->