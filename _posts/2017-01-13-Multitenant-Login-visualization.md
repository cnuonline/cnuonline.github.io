Let's Start visualization of Multi Tenant Users.
Quick Overview of Multi Tenancy models and different styles of implementations of Multi tenant models

![MultiTenant Models](https://cnuonline.github.io/MultiTenant_models.png)

For each tenant, we can separate login's using 

 1. Different URL and seperate DB's for tenant's
 2. One URL with entry of tenant id input box. Option to have Separate db or single db 
 3. Selection of tenants after login, Option to have Separate db or single db 

On All the cases, you need tenantId,username,password

Let's see how it looks.

> 1 . Different URL  . Here tenant id is mapped to the subdomain url, seperate db for each tenant
	
![MultiTenant with URL info having tenant info](https://cnuonline.github.io/Multitenant_URL_based_option_one.png)
> 2 . One URL with entry of tenant id input box.  Here tenant id is mapped to input text box and option to have seperate db or single db for the URL.


![Multitenant with TenantId text box entry](https://cnuonline.github.io/Multitenant_Single_input_box_two.png)

> 3 . Selection of Tenants after Login.  Here tenantId is selection is done through the post login.  Option to have tenant can be separated through db wise or identifier in a table.
	

![Multitenant Post login selection of tenants](https://cnuonline.github.io/Multitenant_PostLogin_Selection_input_box_three.png)
	







