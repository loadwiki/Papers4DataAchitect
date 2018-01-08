Linkedin is an company provided social network service for hundreds million users. Of course it is a big data company. 
LKD creates a full software stack for its data infrastructure. 
It is an excellent learning job to inspect LKD's data infrastructure.
The paper here published in 2012 only include 4 project:
- Voldemort: a scalable and fault tolerant key-value store
- Databus: a framework for delivering database changes to downstream applications
- Espresso: a distributed document store that supports flexible schemas and secondary indexing
- Kafka: a scalable and efficient messaging system for collecting various user activity events and log data

# Voldemort 
Voldemort is a Dynamo style KV store, use dynamic hash to sharding data with no central metadata node, facilitate vector clock to ensure eventual consistency. If you were familiar with Dynamo or cassandra, you can just skip the section.
# Espresso
Espresso is a document store. Its fuctionality just like ElasticSearch and has a little difference. Espresso utilze mysql as its local storage engine and it do has some interal schema. Espresso supports schema modification with compilation constraints which means you can easily expand old schema with new field while the key compoment old schema must kept with little modification. In the meanwhile, ES support schema-free, json style data structure. On the other hand, there is some advantage with mysql storage engine,Voldemort ensure some local transaction feature, you can modify multi records with same internal "resource_id" in a transaction. Voldemort use apache luncene to create local secondary index which optimize for key word query. Voldemort use Databus for replication and Helix for data partion query route and fail over.
# Databus
Databus is a CDC(change data capture) utility to replicate live data from online rdbms(oracle/mysql) to other read replica(KV store, document store). Databus is something like database replication middleware such as datagurd or goldengate with different target. Consumers of databus is another online storage system rather than an instance of slave db. Databus do act like a slave db, provide snapshot or range query with consolidated deltas.
# Kafka
Kafka may be the most famouse open source project created by LKD. Kafka has some common design pattern with traditional MQ or pub/sub system. Kafka consists of producer/broker/consumer compoments. The major difference between Kafka and traditional MQ is that Kafka focous on high performance and scalibility rather than message transaction or broadcast semantic which most MQ concerns. Kafka producer can not ensure a consective message sequence NO. Consumer just pulls message data from broker with an "message offset". Broker sends mesage through a send file api to reduce the overhead of memory copy and buffer slice mamangement.
# Others
Prjoects founded later than the paper or omitted by the paper are proposed too:
- Helix: a framework for cluster management sutable for various distributed system such as distributed data store,distributed message queue
- Dgraph: high available,sharded grpah database scales to multi data center and supports complex distributed queries 
- Ambry:  distributed object storage optimizes for both small immutable objects (50K -100K) and large objects
- Pinot:  a realtime distributed OLAP datastore
