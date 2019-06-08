Let's Start visualization of Multi Tenant Users.
Quick Overview of Multi Tenancy models and different styles of implementations of Multi tenant models

![MultiTenant_SeperateShared_application_Seperate_Database](https://cnuonline.github.io/MultiTenant_SeperateShared_application_Seperate_Database.png)
![MultiTenant_OneShared_application_seperate_database](https://cnuonline.github.io/MultiTenant_OneShared_application_seperate_database.png)
![MultiTenant_OneShared_application_OneShare_Database](https://cnuonline.github.io/MultiTenant_OneShared_application_OneShare_Database.png)

For each tenant, we can separate login's using 

 1. Different URL and seperate DB's for tenant's
 2. One URL with entry of tenant id input box. Option to have Separate db or single db 
 3. Selection of tenants after login, Option to have Separate db or single db 

On All the cases, you need tenantId,username,password and it is all about how are you going to capture it.

Let's see how it looks.

> 1 . Different URL  . Here tenant id is mapped to the subdomain url, seperate db for each tenant . From the illustration, you can capture tenantid through url and login,password from the login form.  Each tenant will be requested to the corresponding url.
	
![MultiTenant with URL info having tenant info](https://cnuonline.github.io/Multitenant_URL_based_option_one.png)

> 2 . One URL with entry of tenant id input box.  Here tenant id is mapped to input text box and option to have separate db or single db for the URL.  From the below illustration, tenant id is captured through input text box along with username ,password. Every tenant will requested through common login form

![Multitenant with TenantId text box entry](https://cnuonline.github.io/Multitenant_Single_input_box_two.png)


> 3 . Selection of Tenants after Login.  Here tenantId is selection is done through the post login.  Option to have tenant can be separated through db wise or identifier in a table.  From the below illustration, tenant will be requested to select the tenant after the login success. Here it will be shown with the list of accessible tenant's and proceed further. This is a good use case for project management app's, wireframe / UI /UX designing app's where each user will be able to access multiple task's from different clients/projects. Citrix - fileshare is a good example for it.
	

![Multitenant Post login selection of tenants](https://cnuonline.github.io/Multitenant_PostLogin_Selection_input_box_three.png)
	







