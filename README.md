# CURT_IOT_Task

### LED
https://wokwi.com/projects/415788943472424961

### Analog read
https://wokwi.com/projects/415821412015298561

### Temperature sensor
https://wokwi.com/projects/415822694782586881

---

# MQTT

### Introduction
Publisher: the host who publishes content
Subscribers: people benefiting from the content
Broker: a third party that connects the publisher to subscribers


---
### Overview
- MQTT: Message Queuing Telemetry Transport
- Definition: Messaging protocol between IOT devices
- It is a lightweight protocol with minimum packet overhead
- Type: Publish/Subscribe

---
### Comm flow
- Not all messages by the publisher are sent to all subscribers
- Topic: subscribers are subscribed to specific topics according to their interests
-  A topic name is better written as a descriptive sequence (ex: car/motor/temp)
- A device can be a publisher and a subscriber in same protocol according to its function in specific scenarios and vice versa
- Messages can be either a **command** or **data**
---
### Features
- Lightweight and efficient
	- Clients uses minimal resources to operate as long as they have a network connection
- Bidirectional
- Highly secure
	- Messages can be encrypted through clients
- Highly Scalable
	- u can easily expand the network (add more devices)
- Reliable message delivery
	- It supports several Quality of Services levels (QoS)

---
### QoS levels
##### Level 0
- Message sent only once, it can be delivered or not
##### Level 1
- Tx keeps sending the message until it receiving an ack from the broker 
##### Level 2
- Tx sends the message and waits for an ack
- If ack is not sent it repeats the message but with a **duplicate flag**

---
### Broker
- It can be an online broker or a broker for a local network
- **Mosquitto** -> software broker for MQTT

---
### Standard Ports
- unsecured -> 1883
- secured     -> 8883

---
### Mosquitto SW
1. Download SW
2. Navigate to installation folder
3. Add a `***.conf` file with required configurations
	- ex: "test.conf"
		`listener 1883`
		`allow_anonymous true`
4. Open command prompt
5. Run `mosquitto -c test.conf -v` 
	- `-v` shows some extra details like (Accuracy, Loss, ...etc) 
6. To connect to the broker u need **IP** and **Port**
