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
