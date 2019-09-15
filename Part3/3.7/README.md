## 3.7

### Why and when to use Kubernetes

Kubernetes is a tool used to orchestrate containers in a large multi-host application environments. As stated on Kubernetes’s official website, it takes care of applications scaling requirements, failover, deployment patterns, and more. With Kubernetes organizations may decrease their application maintenance costs signigicantly since it eliminates the need of running and managing individual VM’s or servers for each service.

E.g. a traditional deployment method such as running all micro-services on one physical server has scalability issues. To scale a service the only way is to start and/or maintain a spare physical server which is might be costly. Moreover if a service crashes, the system administrators must restart the service manually. Also end users may suffer due the service downtime during the recovery. Kubernetes however orchestrates containers automatically and can start new container instances on the fly reducing downtime.

With Kubernetes organizations can achive even more benefits than mentioned above such consistent environment across development, testing and production, portability and observability. Organizations should consider using Kubernetes rather than traditional approaches when handling multiple micro-services. The main advantages are improvements in cooperation between developers and teams due the environment consistency, agile deployment and automated operations which all reduces invested working hours and costs.
