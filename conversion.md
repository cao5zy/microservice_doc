# How do you start a conversion from monolithic to microservices

## Outline
- Introduction
- What does monolithic system look like
- What does microservices system look like
- What are gaps between the development features of monolithic system and microservices system
- My steps for filling the gaps between the development features of monolithic system and microservice system
- Conclusion

### Introduction
This writing aims to explain how to start a conversion from monolithic to microservices. I will explain monolithic and microservices first, and then figure out the gap between the two styles. Finally, I will list some steps to fill the gaps to achieve the conversion.

Before start a conversion, I will try to explain the difference between monolithic system and microservices with following table.

|Area|Monolithic|Microservices|
|--|--|--|
|Programming Language|Only one programming language can be selected. It also means the developers in the team should only master one programming language. |Almost no limit to the choice of programming language. It says we can leverage the capabilities of programming languages for different business domains. |
|Deployment|All libraries are delivered by installation program in the desktop/server. The installation program could be professional `InstallShield` or a simple copy command.|Microservices are deployed in containers over cloud. Docker, ansible, linux, kubernetes and cloud are only the tip of the iceberg.|
|Communications (Technical)|Communications between components in monithic system are almost in threads. It even doesn't need to be managed|Communications between microservices are almost over network. So VPN, authentication of access, aggregation of access should be concerned.|
|Database Design|In most cases, only one database is needed for the monolithic system.|In most cases, one database per microservice.
|Troubleshooting|In most cases, only one log file is required for the monolithic system. The troubleshooting can be done on that log file.|Because each microservice has its log file, the troubleshooting would require multiple log files from multiple microservices. However, this awkward situation has been addressed by the `centralized logging`, such as logstash, flume and so on.|
|Configurations Management|In most case, only several configuration files are for the monolithic system. Settings for the system can be easily controlled over that several configuration files.|At least one configuration file per microservice. Controlling the behavior of the microservices system would involve quite a few configuration files.|
|Monitoring|The monolithic system, in most cases, is deployed as a single executable. It is easy to monitor, for example, it can be described as up/down.|The system of microservices is comprised of quite a few of indenpendent processes. It become hard to monitor. For example, one failure of the system would be caused by one or two microservices which should be quickly identified. So the other tools for monitoring microservices, such as `Prometheus` should be applied.|  


### What does monolithic system look like
I started my career in 2002. The first system is `Hospital Information System` written in `Powerbuilder 7.2`. I didn't know it was a monolithic system at that moment. 

The systems are comprised of libraries. The domains are handled by the libraries. All the data is stored in an instance of Microsoft SQL Server 7.0. 

The system runs as windows execution in the windows 98 desktop OS. The database runs on windows NT 5.0 in a IBM minicomputer.

We have a central server which had a share folder to hold the latest binaries. Each time, when the client desktop started, it will copy the updated files from the share folder. We use this simple way to publish our update.

Each time, when we add a new functionality to the library, we have to rebuild the whole system which would take several minutes. Actually, as a developer, I don't realy care how much time it was taken to build, but I care about the technology it applied. 

About 2 years later, microsfot .net framework became popular. I took some time to study it and found it more powerful than powerbuilder. However, I can't apply C# with .net framework to this system because this system is too big to rewrite in other languages.

To the monolithic system, only one languages can be applied. 

### What does microservices system look like
I really started the development in microservices in last year. The client end runs in the browser. The backend is comprised of microservices that run in containers in Ubuntu server. The client is writen in Javascript, the microservices are written in nodejs and python.

Of course, we can choose other programming languages, such as C# and Java.

### What are gaps between the development features of monolithic system and microservices system
The first gap is technology gap. If I am a junior developer who choose the development style as my first project in career, I will not choose microservice. 

The second gap is culture gap. In the development of monolithic system, although I have heavy burden in understanding the business logic of overall system, I have less burdern to communicate with others. In the development of microservices system, although I just need to carry out limitted functionalities in one microservice, I have more burden to communicate with others.

The third gap is in dependencies. In monolithic system, the word `dependency` even has not been my concern. If I added a functionality into one library, I just rebuilt all libraries which ensures the correct dependencies between libraries. In microservices system, the situation becomes totally different. Each microservice has its own development lifecycle. The dependencies between microservices have to be manually managed.

### My steps for filling the gaps between the development features of monolithic system and microservice system
1. Prepare the test first
2. choose a programming language for the microservice development
3. prepare the technology of container
4. prepare the technology of environment provisioning, such as ansible, chef
5. prepare the technology of vm/cloud
6. choose the first domain for the microservice
7. find a way to manage the version between microservices






