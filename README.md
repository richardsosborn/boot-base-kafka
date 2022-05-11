
- This is an extendable icroservice to access Kafka. 

- Kafka topics are not created automatically by default, this application requires that you create the following topics manually.

`$ bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic improving`<br>
`$ bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 5 --topic partitioned`<br>


#### Sample message received from the 'improving' topic by the basic listeners with groups foo and bar
>Received Message in group 'foo': Hello, World!<br>
Received Message in group 'bar': Hello, World!

#### Sample message received from the 'improving' topic, with the partition info
>Received Message: Hello, World! from partition: 0

#### Sample message received from the 'partitioned' topic, only from specific partitions
>Received Message: Hello To Partioned Topic! from partition: 0<br>
Received Message: Hello To Partioned Topic! from partition: 3

#### Sample message received from the 'filtered' topic after filtering
>Received Message in filtered listener: Hello Improving!

#### Sample message (Serialized Java Object) received from the 'greeting' topic
>Received greeting message: Greetings, World!!
