
**Language Agnostic engineering teams and Istio ServiceMesh**

Today, i want to define the skills required for Successful Product team and decisions took by many engineering leaders while doing the platform evaluation process and hiring the engineers. 

Let me have a question , do you define the platform first & engineering team next ? or other way around , engineering team first & platform defining process next ? 

Every leader envisions the  product in very big picture and when it comes to implementation, they will limit the boundaries to a small world. Example, it is applicable to only Windows machine only , ChromeBrowser only, Android OS only,  OnPremise only...

All the limitations might be due to lack of broader engineering skills ? 
Your hands were tied up and has very few choices while doing Platform selection, Language Selection , Framework selection, Database selection, monitoring & availability tools selection.  is it possible to change the choice while the product was at 70% completion stage ? Let's go through the scientific approach to mitigate the hurdles.

*When you divide the product into tiny modules,  one should keep it in mind , tight coupling of vendors, language, framework will be limiting your success boundaries and faster time to market.*

Let me go through with real time example.

You have a SaaS application (Software as a Service) which is serving your self service shopping app.  For a simple shopping cart app, apart from the basic functional needs like searching & adding to the cart, check out process, you require the following external dependencies.

 - Alerts to customers using SMS, Email ,Push Notifications
 - Payment gateway.
 - Product catalogue with partner merchants
 - Verification of Customer and Merchants
 - Rating and comments authenticity  
 
 Imagine,  all the above features are being provided by AWS, Azure, Google Cloud and they were competitors.  If you are using AWS cloud hosting provider, do you need to leverage only AWS product services only ? Or do you have freedom to choose any thing ? You can choose anything and you have freedom to do it based on the pricing strategy(Operation costs)

This is exactly the same thing which i am correlating with Language Agnostic engineering team. For building a product, if you requires #200 micro services,  do not put a constraint in a such way "All the microservices should be built on Spring or Python or Node JS" 
Figure out a platform which can support  containerisation and freedom to choose the language.

One of them will be ISTIO Platform which provides operational readiness in production and local computer. It brings up of out of box features for networking ,security, scability , monitoring and hosting vendor agnostic.
A good engineer who is comfortable in any language can setup his own container and can be part of the core product team. This makes us to have free choice of selecting *any engineer, any stack*

Finally , it is time to change your questions. 
 - Do you request for engineer with specific field of expertise (Java, Dot Net, NodeJS, Python ) ? or any Engineer who is good at any of the language or framework ?
 - how much depth of knowledge & Hands on Experience on specific tools/stack ?
 
 There are common evaluation criteria for any engineer need to know .
 
 -How the does the HTTP/HTTPS works ?
 -How would handle multiple workloads, parallelism ?
 -How would you the write the code reusable and maintainable ?
 -How would you find out if your code is performance efficient ? Does it leverage the complete cpu and effective process of multithreads ?
 -is your code can run in container and supports horizontal & Verfical scalability?
 -Does it supports caching mechanism ?
 

Next topic will be , how do you move any application to Container ready ? What should be placed in container , is it code or config or stack ?
