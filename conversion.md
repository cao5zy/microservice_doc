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

All of the contents below are limitted my experiences and understanding. Any comments are appreciated.

|Area|Monolithic|Microservices|
|--|--|--|
|Programming Language|Only one programming language can be selected in most cases|Almost no limit to the choice of programming language|
|Deployment|All libraries are delivered by installation program in the desktop/server. The installation program could be professional `InstallShield` or a simple copy command.|Microservices are deployed in containers over cloud. Docker, ansible, linux, kubernetes and cloud are only the tip of the iceberg.|



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






