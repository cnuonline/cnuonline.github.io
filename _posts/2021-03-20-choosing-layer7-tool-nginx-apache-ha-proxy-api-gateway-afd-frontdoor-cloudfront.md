
Picking right tool of Layer 7 & Layer 4 network tools (load balancer, traffic routes)  is challenging especially choosing the opensource, cloud agnostic tech stack . want to share the knowledge on selecting the tools with certain criteria
Criteria:
1. List down the various interaction points - mobile, web, api, intranet traffic, external vendors/parties
2. List down the applications and source of the traffic
3. List down the apps/source which requires strict validation, firewall, token validation, trusted sources(intranet calls) 
Something which can be visualized as a matrix . (Ideally , we require cube kind of a model to represent)

|  |  ReactJS/SPA| Functional API cluster1 |Functional API cluster1|Mobile|External Vendor| Intranet App|
|--|--|--|--|--|--|--|
| Oauth | Yes (allow certain urls) |Yes| Optional |Yes|Yes|No|
| Web App Firewall| Yes (DDos..) |Yes| Yes|Yes|Yes|No|
| Traffic Route| Yes(/images,/html.) |Yes-Route to corresponding cluster| Not Required|Yes|Yes|Yes|
| UnAuthorized Check (Token validate) | Yes  |Yes- precheck at Layer 4| Optional |Yes|Yes|Yes|


Possible tools which has opensource & enterprise version support.
|  | Nginx |Apache|HA Proxy| API Gateway|Azure Frontdoor|AWS CloudFront|
|--|--|--|--|--|--|--|
|Opensource & Free| Yes (only few features) |Yes |Yes |Free (service binding- Long Term contract)| Yes (service binding- Long Term contract) |Yes  (service binding- Long Term contract)|
|Enterprise Support| Yes(NGINX ONE) |No (Good community support)|Yes |Yes(Premium/standard editions) | Yes (Standard) |Yes(Standard)  |
|Oauth support| Yes(Enterprise) |Yes(custom plugin) |Yes |Yes | NA|NA|
|Load Balancer| Yes |Yes |Yes |Yes(Standard) | Yes(Standard)  |Yes(Standard)  |
|Traffic rules| Yes |Yes |Yes |Yes | Yes  |Yes  |
|Reverse proxy support| Yes |Yes |Yes |Yes | NA |NA|
|Throughput| High |Low|High |Yes | High |High |
|Reload config with zero outage| Yes|NA|Yes|Yes | Yes|Yes|
Take a decision based on your budget or already existing relationship with the product tools.


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIwMTQwNDYzNjNdfQ==
-->