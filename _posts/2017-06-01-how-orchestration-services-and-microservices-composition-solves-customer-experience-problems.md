

>How orchestration services and microservices composition solves customer experience problems

Before getting into the details of the topic, let me clear out few things.

 - Orchestration services or Composite services  which calls multiple SOR's (DB,MQ), business Services. 
 - MicroService serves only one unit function & simple usecase.  Atmost, it can have the ability to identify cache or SOR data.

>Is microservices enough to serve all types of clients/customer usecases ?

Yes, we can implement all types of customer requirements including desktop web applications and mobile applications, but with a cost attached. We will be ending up with higher network throughput, increased network latency issues including forced implementation of data visualisation models across all the channels (Web & Mobile..)  . 

On an average , each customer experience usecase needs atleast 6 microservices. Sometimes complex user requirement goes with 15 micro services.

Now just imagine the network throughput for a customer experience usecase. The image below could give you a good picture:

![Simple MicroService Architecture ](https://github.com/cnuonline/cnuonline.github.io/blob/master/Microservice_Architecture.png?raw=true)

>How about the composite services for customer experience use cases ?

Orchestration Service or Composite services or choreograph service are meant to reduce the network latency issues and able to demand to serve the usecase model. They are created to serve the wireframe screens demand and usability issues/feedback from end customer. If mobile requires a different experience, then create orchestration service to serve that model, without having to slice & dice a microservice and disturb the other components.

![Orchestration Service or Choreograph Service](https://github.com/cnuonline/cnuonline.github.io/blob/master/chor_orch2_img.GIF?raw=true)

We don't have to request browser to invoke creditcard microservice, reservation availability micro service,  membership reward micro service. These things can be taken care of by orchestration service.

A mix of Orchestration service and micro service will improve the overall efficiencies & reduces the cost of scaling. You will still have internal network congestion, but it is very negligible when compared with web server & browser congestion. 

>For any suggestions and opinions , you can reach me through [LinkedIn profile](https://www.linkedin.com/in/srinivasulukcloudcomputing/)
 
