**✅ MongoDB Interview Questions & Answers (for 2--12+ years
experience)**

**🟢 Basic-Level Questions**

**1. What is MongoDB?**

**Answer:**\
MongoDB is a NoSQL, document-oriented database that stores data in BSON
(Binary JSON) format. It is schema-less and designed for scalability and
high availability.

**2. How does MongoDB store data?**

**Answer:**\
Data is stored as **documents** (JSON-like format) inside
**collections**. A collection is analogous to a table in RDBMS, and a
document is similar to a row.

**3. What is the difference between MongoDB and a relational database?**

  -----------------------------------------------------------------------
  **MongoDB (NoSQL)**                             **Relational DB**
  ----------------------------------------------- -----------------------
  Schema-less                                     Schema required

  Stores documents                                Stores tables/rows

  Horizontal scaling                              Mostly vertical

  No JOINs (use embedding or linking)             Supports JOINs
  -----------------------------------------------------------------------

**🟡 Intermediate-Level Questions**

**4. What is a replica set in MongoDB?**

**Answer:**\
A **replica set** is a group of MongoDB servers maintaining the same
dataset for **high availability**. It consists of:

- **Primary** node (read/write)

- **Secondary** nodes (replicate from primary)

- **Arbiter** (no data, breaks tie in elections)

**5. Explain indexing in MongoDB.**

**Answer:**\
Indexes support efficient queries. MongoDB supports:

- Single field index

- Compound index (multiple fields)

- Multikey index (arrays)

- Text index

- Geospatial index

- Hashed index

Use explain() to analyze query performance.

**6. What are the different data types in MongoDB?**

- String

- Number (int, long, double, decimal)

- Boolean

- Array

- Object

- Date

- Null

- ObjectId

- Binary data

**7. How do you perform pagination in MongoDB?**

**Answer:**\
Use skip() and limit() in a query:

js

CopyEdit

db.collection.find().skip(10).limit(5);

⚠️ For large data sets, prefer **range-based pagination** using indexed
fields for better performance.

**🔴 Advanced-Level Questions**

**8. What are MongoDB Transactions?**

**Answer:**\
MongoDB supports **multi-document ACID transactions** starting with
version 4.0 (for replica sets) and 4.2+ (for sharded clusters).

js

CopyEdit

const session = db.getMongo().startSession();

session.startTransaction();

try {

// operations

session.commitTransaction();

} catch(e) {

session.abortTransaction();

}

**9. How does sharding work in MongoDB?**

**Answer:**\
Sharding enables horizontal scaling by distributing data across multiple
servers.

- **Shard key** determines partitioning.

- **Config servers** store metadata.

- **Query Router (mongos)** directs queries.

Choose shard keys carefully---avoid low-cardinality or monotonically
increasing keys.

**10. Difference between find() and aggregate()?**

  -----------------------------------------------------------------------
  **find()**            **aggregate()**
  --------------------- -------------------------------------------------
  Simple queries        Advanced data processing

  Limited filtering &   Supports pipeline stages like \$match, \$group,
  projection            \$sort, \$lookup

  Fast                  Slightly slower, more powerful
  -----------------------------------------------------------------------

**11. How do you perform JOINs in MongoDB?**

**Answer:**\
Use \$lookup in aggregation framework:

js

CopyEdit

db.orders.aggregate(\[

{

\$lookup: {

from: \"customers\",

localField: \"cust_id\",

foreignField: \"\_id\",

as: \"customer_info\"

}

}

\]);

**12. How to improve performance in MongoDB?**

- Use proper **indexes**

- Avoid \$where queries

- Use **projection** to limit fields

- Use **connection pooling**

- Avoid unbounded skip()

- Monitor with **MongoDB Atlas/Compass**

**🧠 Scenario-Based Questions**

**13. How would you handle 1:Many relationships in MongoDB?**

**Answer:**\
**Option 1:** Embed (for tightly coupled, small size data)\
**Option 2:** Reference (for large or loosely coupled data)

Example:

json

CopyEdit

{

\"\_id\": 1,

\"title\": \"Post A\",

\"comments\": \[

{\"user\": \"raj\", \"text\": \"Nice post\"}

\]

}

**14. Explain MongoDB's Write Concern and Read Concern.**

- **Write Concern**: Level of acknowledgment (e.g., w:1, w:majority)

- **Read Concern**: Isolation level (e.g., local, majority,
  linearizable)

**15. What is the Aggregation Pipeline?**

**Answer:**\
A framework to process and transform data using stages like:

- \$match, \$group, \$project, \$sort, \$limit, \$unwind, \$lookup

**💡 MCQs or Code-based Quiz (Optional)**

Would you like:

- ✅ 50+ **MCQs** (with answers)?

- ✅ Real-world **coding exercises**?

- ✅ A downloadable **PDF** or GitHub repo?

Let me know if you want this MongoDB Q&A pack in:

- ✅ PDF format

- ✅ Web-based quiz (MCQ format)

- ✅ With diagrams or sample apps (Spring Boot + MongoDB)

Or if you\'d like deep dive questions on:

- MongoDB with **Spring Data**

- MongoDB with **Docker/Kubernetes**

- MongoDB performance tuning or **Atlas setup**

**You said:**

50+ MCQs (with answers)?

**ChatGPT said:**

Updated saved memory

Here are **50+ MongoDB MCQs** with **answers and explanations**, divided
by difficulty level:

**🟢 MongoDB MCQs -- Basic Level (1--20)**

1.  **What does MongoDB store data as?**\
    A. Tables\
    B. Documents\
    C. Columns\
    D. Keys

**Answer:** B. Documents

2.  **Which of the following is not a valid MongoDB data type?**\
    A. String\
    B. Binary\
    C. Double\
    D. Float

**Answer:** D. Float\
(*MongoDB uses \"Double\", not \"Float\" explicitly.*)

3.  **Which command is used to insert a document?**\
    A. db.insertOne()\
    B. db.collection.insertOne()\
    C. db.insert()\
    D. collection.insert()

**Answer:** B. db.collection.insertOne()

4.  **MongoDB is categorized under which type of database?**\
    A. Relational\
    B. NoSQL\
    C. Hierarchical\
    D. Object-Oriented

**Answer:** B. NoSQL

5.  **Which file format does MongoDB use to store documents?**\
    A. JSON\
    B. BSON\
    C. XML\
    D. CSV

**Answer:** B. BSON (Binary JSON)

6.  **The default port of MongoDB is:**\
    A. 3306\
    B. 5432\
    C. 27017\
    D. 8080

**Answer:** C. 27017

7.  **Which command lists all databases?**\
    A. show dbs\
    B. list databases\
    C. db.show()\
    D. display dbs

**Answer:** A. show dbs

8.  **Which of these is a valid MongoDB collection name?**\
    A. 123abc\
    B. system.users\
    C. \@collection\
    D. a\$b\$c

**Answer:** B. system.users\
(*System collections are special but valid.*)

9.  **What command do you use to switch to a database?**\
    A. use mydb\
    B. switch mydb\
    C. select db=mydb\
    D. db = mydb

**Answer:** A. use mydb

10. **MongoDB\'s primary key is always named:**\
    A. id\
    B. \_id\
    C. pk\
    D. mongo_id

**Answer:** B. \_id

11. **Which method retrieves all documents in a collection?**\
    A. db.collection.all()\
    B. db.collection.select()\
    C. db.collection.find()\
    D. db.collection.fetch()

**Answer:** C. db.collection.find()

12. **Which operator is used for \"greater than\"?**\
    A. \$gt\
    B. \>\
    C. \$more\
    D. gt()

**Answer:** A. \$gt

13. **MongoDB stores documents in:**\
    A. Buckets\
    B. Tables\
    C. Collections\
    D. Schemas

**Answer:** C. Collections

14. **Which command shows the indexes on a collection?**\
    A. show indexes\
    B. db.collection.indexes()\
    C. db.collection.getIndexes()\
    D. db.collection.listIndexes()

**Answer:** C. db.collection.getIndexes()

15. **Which statement about MongoDB is false?**\
    A. Supports transactions\
    B. Supports joins\
    C. Uses SQL for querying\
    D. Schema-less

**Answer:** C. Uses SQL for querying

16. **How can you create a unique index?**\
    A. createIndex({field: 1}, {unique: true})\
    B. create({unique: true})\
    C. index.unique()\
    D. unique.createIndex()

**Answer:** A. createIndex({field: 1}, {unique: true})

17. **Which of the following supports full-text search?**\
    A. text()\
    B. \$text\
    C. \$search\
    D. \$lookup

**Answer:** B. \$text

18. **Which of the following is used to perform aggregation?**\
    A. aggregate()\
    B. groupBy()\
    C. sum()\
    D. query()

**Answer:** A. aggregate()

19. **Which method is used to remove a document?**\
    A. deleteOne()\
    B. removeOne()\
    C. erase()\
    D. del()

**Answer:** A. deleteOne()

20. **Which method updates multiple documents?**\
    A. updateMany()\
    B. updateAll()\
    C. multiUpdate()\
    D. setMany()

**Answer:** A. updateMany()

**🟡 Intermediate MCQs (21--40)**

21. **Which stage in aggregation groups documents?**\
    **Answer:** \$group

22. **Which field must be included in every document?**\
    **Answer:** \_id

23. **MongoDB supports ACID transactions starting in version?**\
    **Answer:** 4.0

24. **MongoDB query optimizer chooses a plan based on?**\
    **Answer:** Indexes & cached statistics

25. **How many config servers are required in a sharded cluster
    (recommended)?**\
    **Answer:** 3

26. **What does \$unwind do?**\
    **Answer:** Deconstructs arrays into individual documents

27. **Which operator matches any value in an array?**\
    **Answer:** \$in

28. **Which operator is used for pattern matching?**\
    **Answer:** \$regex

29. **What is the purpose of mongodump?**\
    **Answer:** Backup MongoDB data

30. **What tool restores data from a dump?**\
    **Answer:** mongorestore

31. **What does \$match do in a pipeline?**\
    **Answer:** Filters documents

32. **Which command creates a capped collection?**\
    **Answer:** db.createCollection(\'name\', {capped:true,
    size:5242880})

33. **Which of the following is not a write concern option?**\
    A. w\
    B. j\
    C. fsync\
    D. timeout

**Answer:** D. timeout

34. **What is the command to start a session for a transaction?**\
    **Answer:** db.getMongo().startSession()

35. **What is the default write concern in replica sets?**\
    **Answer:** { w: 1 }

36. **What does ObjectId contain?**\
    **Answer:** Timestamp, machine ID, process ID, counter

37. **What does sh.status() do?**\
    **Answer:** Displays sharding configuration status

38. **Which field should be indexed to speed up a lookup?**\
    **Answer:** Local field in \$lookup

39. **Can MongoDB use compound indexes?**\
    **Answer:** Yes

40. **What is a major disadvantage of using \$skip for pagination?**\
    **Answer:** Performance degrades on large skips

**🔴 Advanced MCQs (41--55)**

41. **How is horizontal scaling achieved in MongoDB?**\
    **Answer:** Sharding

42. **Which field helps determine shard distribution?**\
    **Answer:** Shard key

43. **What happens if you choose a poor shard key?**\
    **Answer:** Data is unevenly distributed → performance issues

44. **Which of the following is not a valid aggregation stage?**\
    A. \$sort\
    B. \$insert\
    C. \$group\
    D. \$project

**Answer:** B. \$insert

45. **Which command is used to explain a query?**\
    **Answer:** db.collection.find({\...}).explain()

46. **Which operator performs logical AND?**\
    **Answer:** \$and

47. **What does the j option in write concern represent?**\
    **Answer:** Journaling acknowledgment

48. **What is the purpose of \$merge in aggregation?**\
    **Answer:** Writes results into a collection

49. **In MongoDB, what is the function of mongos?**\
    **Answer:** Query router in sharded cluster

50. **How are secondary nodes updated in replica sets?**\
    **Answer:** Oplog replication

51. **What is the function of an arbiter node?**\
    **Answer:** Participates in elections but stores no data

52. **What does collStats provide?**\
    **Answer:** Collection-level statistics

53. **How does MongoDB handle atomicity in a single document?**\
    **Answer:** All operations on a single document are atomic

54. **Which command creates a text index?**\
    **Answer:** db.collection.createIndex({ field: \"text\" })

55. **Which of the following supports geospatial queries?**\
    **Answer:** \$geoWithin, \$near, \$geoIntersects

Would you like this:

- ✅ As a **PDF**?

- ✅ In a **web-based quiz app** format?

- ✅ With **diagrams and examples**?

**🧩 1. MongoDB with Spring Data**

**✅ Overview**

Spring Data MongoDB provides seamless integration between **Spring
Boot** and **MongoDB**, abstracting boilerplate code via repositories
and templates.

**🔧 Setup**

**Dependencies (Maven):**

xml

CopyEdit

\<dependency\>

\<groupId\>org.springframework.boot\</groupId\>

\<artifactId\>spring-boot-starter-data-mongodb\</artifactId\>

\</dependency\>

**application.yml:**

yaml

CopyEdit

spring:

data:

mongodb:

uri: mongodb://localhost:27017/mydb

**🧱 Entity Example:**

java

CopyEdit

\@Document(collection = \"employees\")

public class Employee {

\@Id

private String id;

private String name;

private double salary;

private List\<String\> skills;

}

**📦 Repository:**

java

CopyEdit

public interface EmployeeRepository extends MongoRepository\<Employee,
String\> {

List\<Employee\> findBySalaryGreaterThan(double salary);

}

**🧪 Query Methods:**

- findByName()

- findBySalaryBetween()

- findBySkillsIn(List\<String\>)

You can also use \@Query with native Mongo syntax:

java

CopyEdit

\@Query(\"{ \'salary\' : { \$gt: ?0 } }\")

List\<Employee\> findRichEmployees(double threshold);

**🔍 Aggregation Example:**

java

CopyEdit

Aggregation agg = Aggregation.newAggregation(

Aggregation.match(Criteria.where(\"department\").is(\"IT\")),

Aggregation.group(\"skills\").count().as(\"count\")

);

mongoTemplate.aggregate(agg, \"employees\", SkillStats.class);

**💡 Best Practices:**

- Prefer **DTO projection** for performance.

- Use **\@Indexed** for fields involved in queries.

- Avoid large embedded docs (prefer references).

- Leverage **MongoTemplate** for complex logic.

**🧠 Interview Questions (Spring Data MongoDB):**

1.  How do you handle relationships in MongoDB via Spring?

2.  When do you use MongoTemplate vs MongoRepository?

3.  Explain how to implement transactions in Spring Boot with MongoDB.

4.  How can you model embedded vs referenced documents?

5.  How does Spring Data handle custom Mongo queries?

**🐳 2. MongoDB with Docker and Kubernetes**

**✅ Run MongoDB in Docker (Dev Setup)**

**Docker Compose (mongo + UI):**

yaml

CopyEdit

version: \"3.8\"

services:

mongo:

image: mongo:6

ports:

\- \"27017:27017\"

volumes:

\- mongo_data:/data/db

mongo-express:

image: mongo-express

ports:

\- \"8081:8081\"

environment:

ME_CONFIG_MONGODB_URL: mongodb://mongo:27017/

volumes:

mongo_data:

**☸️ Kubernetes MongoDB Deployment**

**mongo-deployment.yaml**

yaml

CopyEdit

apiVersion: apps/v1

kind: Deployment

metadata:

name: mongo

spec:

replicas: 1

selector:

matchLabels:

app: mongo

template:

metadata:

labels:

app: mongo

spec:

containers:

\- name: mongo

image: mongo:6

ports:

\- containerPort: 27017

volumeMounts:

\- name: mongo-pv

mountPath: /data/db

volumes:

\- name: mongo-pv

persistentVolumeClaim:

claimName: mongo-pvc

**mongo-service.yaml**

yaml

CopyEdit

apiVersion: v1

kind: Service

metadata:

name: mongo-service

spec:

selector:

app: mongo

ports:

\- protocol: TCP

port: 27017

targetPort: 27017

type: ClusterIP

**Persistent Volume & Claim (mongo-pvc.yaml)**

yaml

CopyEdit

apiVersion: v1

kind: PersistentVolumeClaim

metadata:

name: mongo-pvc

spec:

accessModes:

\- ReadWriteOnce

resources:

requests:

storage: 1Gi

**🛡 Best Practices in Kubernetes:**

- Use **StatefulSets** for production-grade MongoDB.

- Use **init containers** for replica set initialization.

- Apply **node affinity** for data locality.

- Secure with **TLS + secrets**.

- Use **Liveness/Readiness Probes**.

**⚙️ Connecting from Spring Boot in K8s:**

yaml

CopyEdit

spring:

data:

mongodb:

uri: mongodb://mongo-service.default.svc.cluster.local:27017/mydb

**🧠 Interview Questions (Docker/K8s + MongoDB):**

1.  How do you persist MongoDB data in a Docker/Kubernetes environment?

2.  What are the advantages of using StatefulSets for MongoDB in
    production?

3.  How do you handle readiness checks and health probes for MongoDB in
    K8s?

4.  How would you deploy a MongoDB replica set in Kubernetes?

5.  How does Spring Boot connect to a MongoDB instance running in
    Kubernetes?

**✅ Would you like?**

- A **Spring Boot + MongoDB sample project (GitHub link)?**

- A **Kubernetes YAML pack for MongoDB with StatefulSet + Helm?**

- A **PDF cheat sheet** for interview prep?

- A **Mermaid diagram** of the architecture?

- MongoDB + Spring Boot quiz (MCQ format)?

Let me know, and I'll generate any/all of them for you.

**You said:**

MongoDB + Spring Boot quiz (MCQ format)

**ChatGPT said:**

Here's a **MongoDB + Spring Boot Quiz (MCQ format)** with 30 carefully
crafted questions covering Spring Data, repositories, templates,
configuration, transactions, and more --- tailored for **mid to
senior-level engineers**.

**✅ MongoDB + Spring Boot MCQs**

**🟢 Section 1: Configuration & Setup (Q1--Q5)**

**1. What property is used to set MongoDB URI in application.yml?**\
A. spring.mongodb.uri\
B. spring.mongo.uri\
C. spring.data.mongodb.uri\
D. mongodb.uri\
**✅ Answer:** C

**2. The default port MongoDB uses is:**\
A. 3306\
B. 27017\
C. 5432\
D. 8081\
**✅ Answer:** B

**3. Which annotation is used to map a class to a MongoDB collection?**\
A. \@Entity\
B. \@Document\
C. \@Collection\
D. \@MongoEntity\
**✅ Answer:** B

**4. Spring Boot auto-configures MongoDB if which starter is
included?**\
A. spring-boot-starter-data-jpa\
B. spring-boot-starter-mongo\
C. spring-boot-starter-data-mongodb\
D. spring-data-mongodb\
**✅ Answer:** C

**5. Which class is used to define custom queries in Spring Data
MongoDB?**\
A. JpaRepository\
B. MongoTemplate\
C. JdbcTemplate\
D. DocumentRepository\
**✅ Answer:** B

**🟡 Section 2: Repositories & Querying (Q6--Q15)**

**6. Which interface is extended to create a MongoDB repository?**\
A. JpaRepository\
B. CrudRepository\
C. MongoRepository\
D. ReactiveCrudRepository\
**✅ Answer:** C

**7. What does the following method do? findByAgeGreaterThan(int age)**\
A. Returns all records\
B. Throws exception\
C. Finds documents with age less than given\
D. Finds documents where age is greater than input\
**✅ Answer:** D

**8. Which annotation is used to define native MongoDB queries?**\
A. \@SQL\
B. \@MongoQuery\
C. \@Query\
D. \@NativeQuery\
**✅ Answer:** C

**9. How do you perform full-text search in MongoDB?**\
A. Use \$contains\
B. Use \@TextSearch\
C. Use \$text operator\
D. Use findByText()\
**✅ Answer:** C

**10. What is returned by Optional\<Employee\> findById(String id);?**\
A. Document\
B. Null\
C. Optional wrapper\
D. List\
**✅ Answer:** C

**11. MongoRepository provides:**\
A. Basic CRUD only\
B. Aggregation support\
C. CRUD + paging/sorting\
D. None\
**✅ Answer:** C

**12. Which annotation ensures a field is indexed in MongoDB?**\
A. \@Indexed\
B. \@PrimaryKey\
C. \@Unique\
D. \@Searchable\
**✅ Answer:** A

**13. Which class enables paginated queries?**\
A. SortRequest\
B. Pageable\
C. Cursor\
D. DocumentPage\
**✅ Answer:** B

**14. The method deleteByEmail(String email) is:**\
A. Invalid syntax\
B. Automatically implemented by Spring\
C. Requires implementation\
D. Requires annotation\
**✅ Answer:** B

**15. How are custom query methods named in Spring Data MongoDB?**\
A. SQL-like\
B. HQL-style\
C. Method name parsing\
D. Regex-based\
**✅ Answer:** C

**🔴 Section 3: MongoTemplate & Aggregation (Q16--Q22)**

**16. Which class is used for low-level MongoDB operations?**\
A. MongoMapper\
B. MongoTemplate\
C. MongoService\
D. DocumentHelper\
**✅ Answer:** B

**17. To group and count documents using aggregation, use:**\
A. findAndGroup()\
B. GroupBuilder\
C. \$group stage\
D. project()\
**✅ Answer:** C

**18. To project only selected fields, you use which stage?**\
A. \$match\
B. \$project\
C. \$limit\
D. \$filter\
**✅ Answer:** B

**19. What does \$unwind do in MongoDB aggregation?**\
A. Sorts results\
B. Removes duplicates\
C. Flattens arrays\
D. Joins collections\
**✅ Answer:** C

**20. \$lookup is used for:**\
A. Sorting documents\
B. Filtering by regex\
C. Joins between collections\
D. Pagination\
**✅ Answer:** C

**21. MongoTemplate requires manual:**\
A. Connection pool config\
B. Mapping of all entities\
C. Index creation\
D. Query construction\
**✅ Answer:** D

**22. Which MongoTemplate method updates a single document?**\
A. update()\
B. updateOne()\
C. updateFirst()\
D. set()\
**✅ Answer:** C

**⚙️ Section 4: Transactions, Validation, and Best Practices (Q23--30)**

**23. MongoDB transactions are supported on which deployments?**\
A. Replica Sets only\
B. Standalone only\
C. Sharded clusters only\
D. All deployments\
**✅ Answer:** A

**24. To use MongoDB transactions in Spring, you annotate a method
with:**\
A. \@Transactional\
B. \@MongoTransaction\
C. \@Atomic\
D. \@DocumentTx\
**✅ Answer:** A

**25. MongoDB transactions require:**\
A. Manual rollback always\
B. A session\
C. Only write concern\
D. Index on \_id\
**✅ Answer:** B

**26. To validate a document before save, use:**\
A. \@Valid\
B. \@Validated\
C. javax.validation\
D. All of the above\
**✅ Answer:** D

**27. Which of these improves MongoDB performance?**\
A. Indexing query fields\
B. Avoiding large skip()\
C. Using projections\
D. All of the above\
**✅ Answer:** D

**28. A best practice for MongoDB document modeling is:**\
A. Always embed\
B. Always normalize\
C. Model based on access patterns\
D. Use JSON Schema\
**✅ Answer:** C

**29. Which stage is useful for pagination in aggregation?**\
A. \$limit + \$skip\
B. \$count\
C. \$filter\
D. \$page\
**✅ Answer:** A

**30. What happens if two MongoTemplate updates modify the same field
concurrently?**\
A. Error thrown\
B. Last write wins\
C. Both succeed\
D. Transaction failure\
**✅ Answer:** B
