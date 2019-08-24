# Cloud providers 
Service                           | Azure                       | AWS   | GCP
:---                              | :---                        | :---  | :---
Certifications                    | [Azure certs](#azure-certs) | [AWS certs](#aws-certs) | [GCP certs](#gcp-certs)
Command-line tools                | [Azure PowerShell](azure/azure-ps.md) [Azure CLI](azure/azure-cli.md) | AWS Command Line Interface<br/>AWS Tools for PowerShell| [gsutil](#gsutil) [gcloud](#gcloud)
IaaS                              | Virtual Machines            | Elastic Compute Cloud (EC2) | Compute Engine
PaaS                              | App Service, Cloud Services | Elastic Beanstalk  | App Engine
Containers                        | Container Service, Service Fabric | Elastic Container Service (ECS) | Google Kubernetes Engine
Serverless functions              | Functions                   | Lambda | Functions
Containers                        | Container Service, Service Fabric | Elastic Container Service (ECS) | Google Kubernetes Engine
Virtual networks                  | VNets                       | Virtual Private Cloud (VPC) | Virtual Private Cloud
Load Balancer                     | Load Balancer, Application Gateway | Elastic Load Balancer  | Load Balancing
Private connection to cloud       | ExpressRoute                | Direct Connect  | Interconnect
DNS                               | DNS                         | Route 53              | DNS
CDN                               | CDN                         | CloudFront            | CDN
Object Storage                    | Blob Storage                | Simple Storage Service (S3) | Storage
Block Storage                     | Disk Storage                | Elastic Block Store (EBS) | Persistent Disk
File Storage                      | File Storage                | Elastic File System (EFS) | Filestore (beta)
Reduced-availability Storage      | Cool Blob Storage           | S3 Standard-Infrequent Access, S3 One Zone-Infrequent Access  | Storage Nearline
Archival Storage                  | Archive Blob Storage        | Glacier |  [ Coldline ](https://cloud.google.com/storage/archival/)
Physical data transport           | Import/Export Service, Data Box | Snowball | GCS Transfer appliance [[16](#sources)]
RDBMS                             | SQL Database                | Relational Database Service (RDS), Aurora | SQL, Spanner
NoSQL: Key-value                  | Table Storage               | DynamoDB   | [Firestore](#firestore), [Bigtable](#bigtable)
NoSQL: Indexed                    | [Cosmos DB](#cosmosdb)      | SimpleDB |  [Firestore](#firestore)
Batch Data Processing             | HDInsight, Batch            | Elastic MapReduce (EMR), Batch | Dataproc, Dataflow
Stream Data Processing            | Stream Analytics            | Kinesis |  Dataflow
Stream Data Ingest                | Event Hubs, Service Bus     | Kinesis  | Pub/Sub
Big Data Analytics                | Data Lake Analytics, Data Lake Store | Redshift, Athena  | BigQuery
Messaging                         | Service Bus                 | Simple Notification Service (SNS), Simple Queueing Service (SQS) | Pub/Sub
Monitoring                        | Monitor                     | CloudWatch   | Stackdriver 
Deployment                        | Resource Manager            | CloudFormation   | Deployment Manage

### Certifications
#### AWS certs
[Certification](https://aws.amazon.com/certification/) | Links
:---                                  | :---
AWS Certified Cloud Practitioner      | [Certification]](https://aws.amazon.com/certification/certified-cloud-practitioner/)
AWS Certified Solutions Architect     | [Certification](https://aws.amazon.com/certification/certified-solutions-architect-associate/)
AWS Certified Developer - Associate   | [Certification](https://aws.amazon.com/certification/certified-developer-associate/)
AWS Certified SysOps Administrator - Associate | [Certification](https://aws.amazon.com/certification/certified-sysops-admin-associate/)
AWS Certified Solutions Architect - Professional | [Certification](https://aws.amazon.com/certification/certified-solutions-architect-professional/)
AWS Certified DevOps Engineer - Professional | [Certification](https://aws.amazon.com/certification/certified-devops-engineer-professional/)
AWS Certified Security - Specialty    | [Certification](https://aws.amazon.com/certification/certified-security-specialty/)
AWS Certified Big Data - Specialty    | [Certification](https://aws.amazon.com/certification/certified-big-data-specialty/)
AWS Certified Advanced Networking - Specialty | [Certification](https://aws.amazon.com/certification/certified-advanced-networking-specialty/)
AWS Certified Machine Learning - Specialty | [Certification](https://aws.amazon.com/certification/certified-machine-learning-specialty/)
AWS Certified Alexa Skill Builder - Specialty | [Certification](https://aws.amazon.com/certification/certified-alexa-skill-builder-specialty/)
#### Azure certs
[Certification](https://www.microsoft.com/en-us/learning/browse-all-certifications.aspx) | Links
:---                                  | :---
Azure Administrator Associate         | [Certification](https://www.microsoft.com/en-us/learning/azure-administrator.aspx) Exam: [AZ-103](https://www.microsoft.com/en-us/learning/exam-az-103.aspx)
Azure Security Engineer Associate     | [Certification](https://www.microsoft.com/en-us/learning/azure-security-engineer.aspx) Exam: [AZ-500](https://www.microsoft.com/en-us/learning/azure-security-engineer.aspx#cert-expansion-tab-exam-az-500)
Azure AI Engineer Associate           | [Certification](https://www.microsoft.com/en-us/learning/azure-ai-engineer.aspx) Exam: [AI-100](https://www.microsoft.com/en-us/learning/azure-ai-engineer.aspx#cert-expansion-tab-exam-ai-100)
Azure Data Engineer Associate         | [Certification](https://www.microsoft.com/en-us/learning/azure-data-engineer.aspx) Exams: [DP-200](https://www.microsoft.com/en-us/learning/azure-data-engineer.aspx#cert-expansion-tab-exam-DP-200) [DP-201](https://www.microsoft.com/en-us/learning/azure-data-engineer.aspx#cert-expansion-tab-exam-DP-201)
Azure Data Scientist Associate        | [Certification](https://www.microsoft.com/en-us/learning/azure-data-scientist.aspx) Exam: [DP-100](https://www.microsoft.com/en-us/learning/azure-data-scientist.aspx#cert-expansion-tab-exam-DP-100)
Azure Developer Associate             | [Certification](https://www.microsoft.com/en-us/learning/azure-developer.aspx) Exam: [AZ-203](https://www.microsoft.com/en-us/learning/azure-developer.aspx#cert-expansion-tab-exam-az-203)
Azure DevOps Engineer Expert          | [Certification](https://www.microsoft.com/en-us/learning/azure-devops.aspx) Exam: [AZ-400](https://www.microsoft.com/en-us/learning/azure-devops.aspx#cert-expansion-tab-exam-az-400)
Azure Solutions Architect Expert      | [Certification](https://www.microsoft.com/en-us/learning/azure-solutions-architect.aspx) Exams: [AZ-300](https://www.microsoft.com/en-us/learning/azure-solutions-architect.aspx#cert-expansion-tab-exam-az-300), [AZ-301](https://www.microsoft.com/en-us/learning/azure-solutions-architect.aspx#cert-expansion-tab-exam-az-301)
#### GCP certs
[Certification](https://cloud.google.com/certification/)| Links
:---                                  | :---
Associate Cloud Engineer              | [Certification](https://cloud.google.com/certification/cloud-engineer) [Exam](https://cloud.google.com/certification/guides/cloud-engineer/)
Professional Cloud Architect          | [Certification](https://cloud.google.com/certification/cloud-architect/)
Professional Data Engineer            | [Certification](https://cloud.google.com/certification/data-engineer/)
Professional Cloud Developer          | [Certification](https://cloud.google.com/certification/cloud-developer/)
Professional Cloud Network Engineer   | [Certification](https://cloud.google.com/certification/cloud-network-engineer)
Professional Cloud Security Engineer  | [Certification](https://cloud.google.com/certification/cloud-security-engineer/)
Professional Collaboration Engineer   | [Certification](https://cloud.google.com/certification/collaboration-engineer)
## Services
### Command-line tools
#### AWS Command Line Interface and AWS Tools for PowerShell
[[17](#sources)]
#### gsutil
gsutil is a Python application that enables command-line access to Cloud Storage [[15](#sources)].\
`gsutil` uses the prefix `gs://` to indicate a resource in Cloud Storage:
```
gs://BUCKET_NAME/OBJECT_NAME
```
#### gcloud
[gcloud command-line tool](https://cloud.google.com/sdk/gcloud/)
#### CosmosDB
Microsoft Azure NoSQL database service optimized for mobile and web applications that offers graph, document, and key-value APIs [[11](#sources)].
#### Firestore
NoSQL Document database service offering high performance and automatic scaling intended for serverless mobile and web application development with Cloud App Engine.
  - **History**: Firestore was released from beta in early 2019 and combines and improves upon functionality of previous products named **Cloud Datastore** and **Firebase Realtime Database** [[8,9](#sources)]. Firestore features a compatibility mode that emulates the behavior of Datastore in accessing Firestore's storage layer while removing some of Datastore's limitations.
  - **Queries** [[3](#sources)]
    - Queries in Firestore are intended to be used to find documents stored in one specific collection or sub-collection. 
    - A query that spans multiple sub-collections ("collection group query") was not possible until recently, but the field has to be specified as having a scope of "Collection group" within GCP, and there is a limit of (about) 200 for these queries. 
    - An index is created for every field in every document added to a collection, which results in very fast query times that are proportional to the number of **results**, not records searched. But this means that there is no native way to perform wildcard searches or OR queries. For common instances of such queries, Google recommends adding a field that contains that result for each record 
    - Firestore's structure ensures that equality searches are highly performant.
    - "Inequality searches" present a challenge for Firestore. For some queries that combine conditions on more than one field (i.e. restaurants within a certain range of a location), Firebase will create a "composite index" (only within the index, the document itself is not affected) automatically to facilitate searches on those fields.
  - **Pricing**: Firestore primarily charges based on the number of reads, writes, and deletes performed on the database, each of which have a different unit charge. [[10](#sources)]
#### BigTable
GCP Realtime database used for Big Data [[7](#sources)].
  - **History**: BigTable evolved out of Google's need to ensure access to petabytes of data in its web search business line. It was described in a 2006 research paper that ended up launching the entire NoSQL industry. In 2015 it was made available as a service to cloud customers. [[4](#sources)]
  - **Queries**: BigTable doesn't support secondary indexes [[5,6](#sources)]
#### App Engine
Google Cloud Platform Platform-as-a-Service offering.

Video | Link
:---  | :---
Get to know Google App Engine | [YouTube](https://youtu.be/2PRciDpqpko) 

#### Compute Engine

Video | Link
:---  | :---
Getting Started with Google Cloud Compute Engine | [YouTube](https://youtu.be/1XH0gLlGDdk)
#### Coldline

## Glossary
Term              | Definition  
:---              | :---
Classless Inter-Domain Domain Routing | style of describing IP address ranges where a slash followed by a number follows the IP address (i.e. `10.0.0.0/8`) describes what portion of an IP address is variable and what portion describes the host [[A](#sources): 280]
document store    | also "document-oriented database", a type of **NoSQL database** that relies on the concept of the record as **document**, whose **content** may differ in format and structure from document to document. Documents are placed within a **collection**, and each document is addressed via a unique key.
Elasticity        | ability to increase or decrease the __instance count or size__ of existing resources based on fluctuations in traffic or load, or in resource workload 
FaaS              | **Function as a Service**
Function as a Service | **serverless** architecture
Fault tolerance   | a system's ability to __continue operating properly__ when one or more of its components fails [[7](#sources)]
High availability | maintaining __acceptable continuous performance__ despite temporary load fluctuations or failures in services, hardware, or data centers | 
IaaS              | ("eye-az") Infrastructure as a Service 
PaaS              | ("paz") cf. **Platform as a Service**
Platform as a Service | software design pattern where a third-party service (i.e. Heroku, [Azure Web Apps](), and AWS [Elastic Beanstalk](#elastic-beanstalk)) eliminates the need for managing infrastructure but unlike **serverless architecture**, does not scale automatically. Typically an application deployed over PaaS is running on at least one server at all times.
SaaS              | ("saz") Software as a Service 
Scalability       | ability to increase the __instance count or size__ of existing resources [[7](#sources)
Scale out         | increase __instance count__ of existing resources: non-disruptive [[7](#sources)]
Scale up          | increase __instance size__ of existing resources: __disruptive__ [[7](#sources)]
Serverless architecture | software design pattern where applications are hosted by a third-party service and are executed only when needed. Typically used for simple, transaction-type functions that are run often.
zone              | a part of the domain namespace delegated to a legal entity (person or organization) who is responsible for maintaining it, i.e. Top-Level Domains (".com"), second-level domains ("example.com"), and subdomains; also an administrative function allowing for granular control of DNS components [[14](#sources)]

## Sources
  1. Washam, Michael; Tuliani, Jonathan; Hoag, Scott. _Exam Ref AZ-103 Microsoft Azure Administrator_. [AZ-103](sources/az-103.md)
  2. "Zero to App: Live Coding an App with Firebase (Firebase Dev Summit 2017)". [YouTube](https://www.youtube.com/watch?v=VTkM5BbnslU)
  3. "How do queries work in Cloud Firestore/ | Get to Know Cloud Firestore #2". [YouTube](https://youtu.be/Ofux_4c94FI): 2018/05/30.
  4. "Introduction to Google BigTable: Best Uses, Design, and Demo". [YouTube](https://www.youtube.com/watch?v=1qieV-WCU_w)
  5. "The Right Bigtable Index Makes All the Difference". [YouTube](https://www.youtube.com/watch?v=oxC_iTLGtLA): 2019/01/17.
  6. "The right Cloud Bigtable index makes all the difference". [Medium](https://medium.com/@duhroach/the-right-cloud-bigtable-index-makes-all-the-difference-3bcabe9bd65a): 2019/01/17.
  7. "System Properties Comparison Google Cloud Bigtable vs. Google Cloud Firestore". [db-engines.com](https://db-engines.com/en/system/Google+Cloud+Bigtable%3BGoogle+Cloud+Firestore)
  8. "Introducing Firebase Realtime Database". [YouTube](https://youtu.be/U5aeM5dvUpA): 2016/05/18.
  9. "Cloud Firestore vs the Realtime Database: Which one do I use?". [The Firebase Blog](https://firebase.googleblog.com/2017/10/cloud-firestore-for-rtdb-developers.html): 2017/10/03.
  10. "Cloud Firestore Pricing | Get to Know Cloud Firestore #3". [YouTube](https://youtu.be/6NegFl9p_sE): 2018/06/27.
  11. "Azure Friday | Azure Cosmos DB with Scott Hanselman". [YouTube](https://youtu.be/4fRKzcU__jY): 2017/06/27.
  12. "Archival cloud storage: Nearline & Coldline". [Google Cloud](https://cloud.google.com/storage/archival/)
  13. "Linux Academy: Microsoft Azure Concepts". [Udemy](https://www.udemy.com/linux-academy-microsoft-azure-concepts/)
  14. "DNS zones explained". [Pocket](https://app.getpocket.com/read/2495535941) -> [ns1.com](https://ns1.com/resources/dns-zones-explained)
  15. "gsutil tool". [Google Cloud](https://cloud.google.com/storage/docs/gsutil).
  16. "Uploading files to GCS (Cloud Storage Bytes". [YouTube](https://youtu.be/nmZxfuFIP08).
  17. "SysAdmin & Hybrid Cloud Special". [AWS TechChat](../sources/README.md#aws-53)