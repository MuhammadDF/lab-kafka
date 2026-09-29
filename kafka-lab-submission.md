# Kafka Lab Submission

**1. What Kafka topic did you use, and which cities did you add to the producer data?**

Your answer: Topic: lab-kafka-mfouly and I added Charlotte, NC and Minya, Egypt

**2. Paste one message read by your notebook consumer and one complete line produced by `kcat`, including its offset.**

Your answer: 

Message read by notebook consumer: {'city': 'Minya', 'timestamp': '2026-09-29 03:58:14', 'temperature_f': 95} offset 0
One complete line produced by kcat: 2: {"city": "Minya", "timestamp": "2026-09-29 03:49:00", "temperature_f": 95} offset 2

**3. What do the topic and offset in your `kcat` output identify? How would a stored offset help a consumer resume after disconnecting?**

Your answer: The topic identifies the named stream containing the message. The offset identifies the message’s position within that topic. A stored offset can help a consumer resume after disconnecting because it is almost like a checkpoint of how far the consumer read.

**4. Which `auto_offset_reset` value did you use? Compare its behavior with one other value and explain when this setting takes effect.**

Your answer: I used earliest, which starts at the oldest message still available in a partition. By comparison, latest starts at the end and waits for new messages. This setting takes effect when the consumer group has no saved offset for a partition, or when its saved offset is no longer valid. A valid saved offset takes precedence.

**5. What local Kafka address did the notebook use, and how did the SSH tunnel make the remote broker available at that address?**

Your answer: The notebook used localhost:9092. The SSH tunnel listened on port 9092 in the lab VM and forwarded connections through SSH to port 9092 on the remote server. This let the notebook reach the remote Kafka broker using a local address.
