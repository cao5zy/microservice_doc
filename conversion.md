# How do you start a conversion from monolithic to microservices

Before starting a conversion from monolithic system to microservices system, let's take a look at the difference between them  with the following table.

## Differences between monolithic system and microservices system

|Area|Monolithic|Microservices|
|--|--|--|
|Programming Language|Only one programming language can be selected. It also means the developers in the team should only master one programming language. |Almost no limit to the choice of programming language. It says we can leverage the capabilities of programming languages for different business domains. |
|Deployment|All libraries are delivered by installation program in the desktop/server. The installation program could be professional `InstallShield` or a simple copy command.|Microservices are deployed in containers over cloud. Docker, ansible, linux, kubernetes and cloud are only the tip of the iceberg.|
|Communications (Technical)|Communications between components in monolithic system are almost in threads. It even doesn't need to be managed|Communications between microservices are almost over network. So VPN, authentication of access, aggregation of access should be concerned.|
|Database Design|In most cases, only one database is needed for the monolithic system.|In most cases, one database per microservice.The `Domain Driven Design` is highly recommended in the databases design over microservices. |
|Troubleshooting|In most cases, only one log file is required for the monolithic system. The troubleshooting can be done on that log file.|Because each microservice has its log file, the troubleshooting would require multiple log files from multiple microservices. However, this awkward situation has been addressed by the `centralized logging`, such as logstash, flume and so on.|
|Configurations Management|In most case, only several configuration files are for the monolithic system. Settings for the system can be easily controlled over that several configuration files.|At least one configuration file per microservice. Controlling the behavior of the microservices system would involve quite a few configuration files. So the tools, such as ansible, is required for provisioning with managed configuration.|
|Monitoring|The monolithic system, in most cases, is deployed as a single executable. It is easy to monitor, for example, it can be described as up/down.|The system of microservices is comprised of quite a few of independent processes. It become hard to monitor. For example, one failure of the system would be caused by one or two microservices which should be quickly identified. So the other tools for monitoring microservices, such as `Prometheus` should be applied.|  

## The start for conversion
Actually, this is a long journey to convert a monolithic system to microservices system. Although there are quite a few particularities to individual cases, there are generally following points for your reference to start conversion.
1. Get the approval and support from the head
2. Build the DevOps culture
3. Equip with the knowledge and experiences on cloud, container, ansible, logstash, prometheus, kubernetes and domain driven design.
4. Make a detailed plan for implementation and go step by step.

## Conclusion
It is found that the conversion from monolithic system to microservices system is not easy. Kinds of knowledge and experiences are required. However, microservices are driven by business. No matter how hard it would be, any solutions that can respond to the rapid changes in business should be adopted. 
