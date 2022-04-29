<h1 id="scalability">Scalability</h1>
Scalability means the application’s ability to <b>handle and withstand increased workload without sacrificing performance</b>.<br>
For example, if your app takes x seconds to respond to a user request. It should take the same x seconds to respond to each of your app’s million concurrent user requests. In other words, with increase in the number of users, the response time of the application should not increase.<br><br>
The app’s back-end infrastructure should not crumble under a load of a million concurrent requests. It should scale well when subjected to a heavy traffic load and maintain the system’s latency.<br><br><br>
To scale well, an application needs <b>solid computing power</b>. The servers should be powerful enough to handle increased traffic loads.<br>
There are two ways to scale an application:<br>
- Vertically<br>
- Horizontally<br><br><br>

<h2>Vertical Scaling</h2>
Adding more power to our server. <br>
Eg:- increasing RAM from 16 GB to 32 GB<br><br>
Ideally, when the traffic starts to build on the app, the first step should be to scale vertically. <br>
<blockquote>Vertical scaling is also called <b><i>scaling up</i></b></blockquote>
In this type of scaling, we augment the power of the hardware running the app. This is the simplest way to scale as it doesn’t require any code refactoring or the need to make any complex configurations and so on.<br><br><br>
However, there is only so much we can do when scaling vertically. There is a limit to the compute power we can augment for a single server.<br><br>
A good analogy would be to think of a multi-story building. We can keep adding floors to it but only up to a certain point. What if the number of people in need of a flat keeps rising? We can’t scale the building up to the moon for obvious reasons.<br>
Now is the time to build more buildings. <br> This is where horizontal scalability comes in.
<br><br><br><br><br><br><br><br><br><div align="center">1</div>
When the traffic is too large to be handled by a single server, we bring in more servers to work together.<br><br>
<h2>Horizontal Scaling</h2>
Adding more hardware to the existing hardware resource pool. This increases the computational power of the system as a whole.<br><br>
With this, the increased traffic influx can be efficiently dealt with. And there is no limit to how much we can scale horizontally, assuming we have infinite resources. We can keep adding servers after servers, setting up data centers after data centers.<br><br>
Horizontal scaling also allows us to scale dynamically in real-time as the traffic on our website climbs and drops over a period of time. Dynamic scaling is not possible when scaling vertically.<br><br>
<h3>Cloud elasticity</h3>
The most prominent reason cloud computing became mainstream in the industry is the ability of the cloud to scale dynamically. In case of the traffic climb, the cloud adds additional servers to the hardware resource pool and when it drops, the servers added are removed.
The ability to use and pay only for the hardware resources used by the website got popular with businesses for obvious economic reasons.
The process of adding and removing servers, stretching and returning to the original infrastructural computational capacity, on the fly is popularly known as cloud elasticity. It saves businesses truckloads of money every single day.
<br><br><br>
<table>
<th><td>Horizontal Scaling</td><td>Vertical Scaling</td></th>
<tr><td>1</td><td>Multiple servers<br>Load Balancing is required</td><td>Single server<br>Load Balancing is not required</td></tr>
<tr><td>2</td><td>Hard to manage as it's a distributed environment and need administrative efforts, monitoring</td><td>Not that easy to manage as no need to make any complex system configurations</td></tr>
<tr><td>3</td><td>Highly available<br>(Resilient)</td><td>Availability risk as the single server can go down and the entire website be going offline <br> (Single point of failure)</td></tr>
<tr><td>4</td><td>Scales well</td><td>Scales well only to a certain amount coz of hardware limitations<br></td></tr>
</table>
<br><br><br><br><br><br><br><div align="center">2</div>
<h3>Concept of Distributed Memory</h3>
When writing applications for distributed systems, we should support application-wide memory instead of server-wide memory. As if the server goes down, the app is left in an inconsistent state. So, <b>to maintain a consistent state</b>, we use distributed memory like Redis, Memcache, etc... <br><br><br><br><br><br><br><br><br><br>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><div align="center">3</div>
<h1>Monolith & Microservices</h1>
<h2>Monolithic Architecture</h2>
An application has a monolithic architecture if it contains the entire application code in a single codebase.
<br><br>
A monolithic application is a self-contained, tightly coupled software application. This is unlike the microservices architecture, where every distinct feature of an application may have one or more dedicated microservices powering it.
<br><br><br>
<h3>Advantages</h3>
1. Monolithic applications are simple to develop, test, deploy, monitor and manage since everything resides in one repository.<br>
2. Things are relatively simple when dealing with one repository averting the complexity associated when handling and monitoring multiple components deployed separately.<br><br><br>

<h3>Disadvantages</h3>
1. <b>Continuous deployment</b> is a pain in monolithic applications as even a minor code change in a certain application layer or a feature necessitates a re-deployment of the entire application.<br>
2. The downside of re-deployment of the entire application is that we need to perform a thorough <b>regression testing of the whole application</b> after the deployment is done. A minor code change in one feature can potentially impact the functionality of other features significantly since all the features are tightly coupled with each other.<br>
3. Monolithic applications have a <b>single point of failure</b>. A bug in any of the application features can bring down the entire application.<br>
4. Maintenance and scalability are a challenge in monolith apps as all the components are so tightly coupled with each other. As the code size increases, things get trickier to manage.<br>
5. Building complex applications with a monolithic architecture is tricky since multiple technologies and programming languages need to be leveraged to implement the respective features of an application.<br>
Using multiple programming languages in a single codebase becomes a mess also often times not possible. <b> Heterogeneous technologies</b> have compatibility issues and microservices architecture suits best to leverage them.<br>
Eg:- It is mostly not even possible to use Java and NodeJS together in a single codebase.

<br><br><br><br><br><br><br><div align="center">4</div>
<h2>Microservices Architecture</h2>
In a microservices architecture, different features of an extensive service like Facebook are deployed separately as smaller loosely coupled services called microservices. These microservices work in conjunction to form a large distributed online service as a whole.<br><br>
Every service has a single responsibility of running a specific feature and is separated from other services facilitating a loosely coupled architecture.<br><br>
Every microservice interacts with each other via a REST API gateway interface.<br><br><br>
<h3>Advantages</h3>
1. This particular architecture facilitates easier, <b>cleaner app maintenance, feature development, testing</b>, and deployment of individual modules.<br>
2. Since microservices is a loosely coupled architecture, there is <b>no single point of failure</b>. Even if a few services go down, the application as a whole would still be up. Also, every microservice ideally has a separate database. <br>
3. Leverage the heterogeneous technologies<br>
4.  When application modules/features are separate, they can be assigned to dedicated teams with minimal fuss, <b>smoothing out the development</b> process.<br>
5. The deployments can be independent and continuous.<br>
6. Scalability becomes easy. The architecture is inherently designed to scale. Services that need scaling can be scaled independently without affecting other services.<br><br><br>

<h3>Disadvantages</h3>
1. Microservices is a distributed environment with several services powered by clusters of servers. This makes system management and monitoring complex.<br>
We need to set up additional components to manage microservices, such as a node manager like Apache Zookeeper, a distributed tracing service for monitoring the nodes, etc.<br>
2. As it's a distributed design, things are eventually consistent across the nodes. Strong consistency is hard to guarantee.

<br><br><br><br><br><br><br><br><br><br><br><br><div align="center">5</div>
<h2>When to pick what ?</h2>
Monolithic applications fit best for use cases when the application is not that complex (having limited features) and will not require any serious expansion in the near future.<br><br>
The microservice architecture fits best for complex use cases; for apps that need to expand quick from adding new features standpoint. <br><br><br>
Often during the initial stages of a business, teams choose to move forward with a monolithic architecture, intending to branch out into a distributed microservices architecture later.<br>
Example:- LinkedIn <br><br><br>
In the present computing landscape, applications are built and deployed on the cloud. Also, businesses have to move fast. A wise decision is to pick the loosely coupled stateless microservices architecture from the start if we have multiple distinct features in our application and expect things to grow at a rapid pace in the future.
