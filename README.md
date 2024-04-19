How many data your publlsher program will send to the message broker in one
run?  
In the provided Rust code, the main function initializes a publisher p for the CrosstownBus message broker and then publishes five UserCreatedEventMessage events using the publish_event method of the publisher.  

Therefore, in one run of the program, the publisher sends five data messages to the message broker.  

The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber
program, what does it mean?  
The URL "amqp://guest:guest@localhost:5672" is commonly used to connect to a message broker using the Advanced Message Queuing Protocol (AMQP). In this URL:  
1. "amqp://" specifies the protocol, which is AMQP.  
2. "guest:guest" specifies the username and password for authentication. In this case, both the username and password are "guest".  
3. "localhost" specifies the hostname or IP address of the machine where the message broker is running. "localhost" means the message broker is running on the same machine as the program.  
4. "5672" specifies the port number on which the message broker is listening for incoming connections. This is the default port for AMQP.  
When the same URL is used in both the publisher and subscriber programs, it means that both programs are connecting to the same message broker instance running on the same machine, using the same authentication credentials and port number. This ensures that the publisher can publish messages to the same message broker instance to which the subscriber is subscribed.  

![Rabbit](rabbit.png)  
![Subscrriber](subscriber.png)  
![Rabbit_Subs](rabbit_subs.png)  
The image above shows that after the publisher is run. Publisher will send the data that has been hard coded in its code to the message queue. Subscribers who are connected to the message queue will get the data from the message queue and output it in the console according to the code that has been created.  
![Rabbit_Chart](rabbit_chart.png)  
In the second graph, it is shown that there is an increase in messages in a time interval. This is related to the cargo run implemented in the publisher project. Where it can be seen that every time the publisher is implemented, there will be an increase in the message rate on rabbitMQ which is useful as a message queue.  
![Rabbit_Slow](rabbit_slow.png)  
In the picture above, it can be seen that at one time there were 20 messages in the queue. This happens because the subscriber needs more time to manage each event in the message queue so that there is a buildup of messages because it is faster for the publisher to publish a message than for the subscriber to create a message.  
![1](1.png)  
![2](2.png)  
![3](3.png)  
![Rabbit_3_Sub](3_sub.png)  
