---

title: Scaling framework for querying
abstract: Certain example embodiments described herein relate to techniques for scaling processing systems. For instance, in certain example embodiments, a scaling master receives a user-specified scaling and/or alerting query. The scaling and/or alerting query is transmitted to scaling agents at respective ones of the processing elements, the transmission using the connection layer. Each of the scaling agents executes the at least one scaling and/or alerting query. Each of the scaling agents reports a result of the executing to the scaling master using the connection layer. The scaling master forms a scaling decision based on the result reported by each of the scaling agents.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09514018&OS=09514018&RS=09514018
owner: Software AG
number: 09514018
owner_city: Darmstadt
owner_country: DE
publication_date: 20140128
---
Certain example embodiments described herein relate to techniques for scaling processing systems having a plurality of processing elements.

Scalability is an important feature for many systems. Scalability generally refers to the capability to add processing resources e.g. computers processors virtual machines memory processes threads etc. to a system such that for example the workload e.g. processing demand presented to the system can be handled in accordance with certain performance criteria. Performance criteria may include processing delay levels throughput levels system and or processor capacity used and the like. An example scalable system may be able to add processing elements such as for example web servers when the incoming workload to a current pool of web servers that serve incoming requests exceeds a first threshold and to also remove web servers from the pool when the workload drops below a second threshold.

In example scalable systems alerts may be generated when either the processing resources or the incoming workload reaches certain configured thresholds. For example an alert may be generated when all processors in the system are at 80 capacity. Alerts are typically intended to warn an operator regarding a condition of the processing system.

In cloud environments scalability may be even more important than in non cloud environments. Many techniques are known for achieving scalability and alertness e.g. ability to generate alerts when system conditions are detected in cloud management software. Such features are often shipped as a feature e.g. in the box feature within hardware and or software that is sold. Many applications allow for users to configure scale alert conditions or related parameters using an administrative user interface. For example Amazon Web Services AWS uses the CloudWatch console for defining and generating alarms alerts. However in AWS configuring policies for dynamic scaling may involve numerous steps to be performed by the user.

A problem with many of the currently available cloud management software is that the scaling and or alerting decision logic module is shipped as a feature within the box e.g. incorporated into the software and or hardware and users e.g. operator have limited control over the logic module if any. They either provide simple UI based or complicated commands APIs based scaling solution which may not provide for evaluating complex scaling conditions.

Further many of the currently available cloud management software provide little or no support for implementing and configuring metric sources for custom metrics.

Moreover many of the currently available cloud management software may not allow for the eviction policy e.g. policy for evicting processing elements to be customized and as a result may evict processing elements that are not the best suited for being evicted. In many of the currently available systems no clear indication on how final scaling conclusion is drawn.

Thus it will be appreciated by those skilled in the art that there is need for improved techniques for providing scalability and or alerts in processing systems e.g. in ways that overcome the above described and or other problems.

Certain example embodiments provide a scaling engine that may be incorporated into hardware and or software in order to provide scaling and or alerting decision services to cloud management platforms. Certain example embodiments may also provide extension points to the scaling engine that may be used to customize various aspects of scalability and alerts such as for example implementation of a connection layer between scalability elements summation policy eviction policy and metric source can be plugged and powerful as it provides a structured query language.

In certain example embodiments a scalable system having a plurality of communicatively coupled processing elements is provided. The system includes at least a scaling master a plurality of scaling agents and a connection layer providing one or more interfaces for communication between the scaling master and the plurality of scaling agents over a network. Each scaling agent may be located at a respective one of the plurality of communicatively coupled processing elements. The scaling master is configured to transmit using the connection layer at least one user specified scaling and or alerting query to each scaling agent. Each scaling agent is configured to execute the at least one scaling and or alerting query received from the scaling master and to report using the connection layer a result of the execution to the scaling master. The scaling master is further configured to receive each result and to form a scaling decision based on the results.

According to certain example embodiments the scaling master may be further configured to receive the at least one scaling and or alerting query from a user input device or from a configuration file.

According to certain example embodiments the at least one scaling and or alerting query may combine plural scaling and or alerting expressions using one or more conditional operators.

According to certain example embodiments the scaling master may be further configured to transmit one or more scaling commands based on the formed scaling decision to respective ones of the plurality of scaling agents.

According to certain example embodiments the scaling master may be configured to form the scaling decision by performing operations including aggregating the received results and making the scaling decision based on the aggregated result.

According to certain example embodiments the scaling master may form the scaling decision by performing operations including selecting the received results for the aggregating based on a flow control operation.

The flow control may be a closed loop flow control and the scaling decision may be based on reducing a difference between a configured desired metric and a measured metric determined from the selected results according to certain example embodiments.

The flow control may be an open loop flow control and the scaling decision may be further based on a configured number of reported results selected during a first predetermined time interval with respective first predetermined time intervals being separated by a second predetermined time interval according to certain example embodiments.

According to certain example embodiments the aggregating may be performed in accordance with a configurable policy.

According to certain example embodiments the connection layer may include a structured query language and the at least one scaling and or alerting query may be specified in the structured query language.

According to certain example embodiments each scaling agent may be configured to compile the received at least one scaling and or alerting query and to execute the compiled query.

According to certain example embodiments the scaling master may be further configured to calculate a number of processing elements to be evicted to maintain a desired load. The calculating may be based on an average load in the processing elements. The processing elements may be ranked in accordance with a weighted average load and the processing elements to be evicted are selected in accordance with the ranking.

According to certain example embodiments the scaling master may be configured to transmit a command to stop the executing of the at least one scalability and or alerting query. The command may include an identifier for the at least one scaling and or alerting query.

According to certain example embodiments the scaling agent may be further configured to schedule the at least one scaling and or alerting query for subsequent execution at a specified time. The executing of the scheduled at least one scaling and or alerting query may occur subsequently at the specified time.

In certain example embodiments a method for scaling a processing system having a plurality of communicatively coupled processing elements is provided. The scaling master receives a user specified scaling and or alerting query and transmits the query to scaling agents at respective ones of the plurality of processing elements using the connection layer. Each scaling agent executes the at least one scaling and or alerting query and reports a result of the executing to the scaling master using the connection layer. The scaling master forms a scaling decision based on the result reported by each of the scaling agents.

According to certain example embodiments the scaling master may transmit one or more scaling commands based on the formed scaling decision to respective ones of the plurality of scaling agents.

According to certain example embodiments the forming a scaling decision may include aggregating the reported results and making the scaling determination based on the aggregated result.

According to certain example embodiments the connection layer may include a structured query language and the at least one scaling and or alerting query may be specified in the structured query language.

In certain example embodiments there is provided a non transitory computer readable storage medium tangibly storing instructions that when executed by at least one processor of a system perform a method for sealing a processing system as described herein. The method may includes for instance the scaling master receiving a user specified scaling and or alerting query and transmitting the query to scaling agents at respective ones of the plurality of processing elements using the connection layer. Each scaling agent executes the at least one scaling and or alerting query and reports a result of the executing to the scaling master using the connection layer. The scaling master forms a scaling decision based on the result reported by each of the scaling agents.

These aspects features and example embodiments may be used separately and or applied in various combinations to achieve yet further embodiments of this invention.

Certain example embodiments relate to improving scalability and alerting in processing systems. The techniques of certain example embodiments provide simple yet powerful application programming interfaces APIs around query policy for cloud management platforms e.g. Rightscale Scalr etc. . These APIs can make effective scaling and alerting decisions for the topology cloud management platforms CMP s are managing hence resulting in a scalable infrastructure.

This may improve the scalability e.g. cloud bursting and alerting aspects of the cloud management software and provide more control to users as it may help decouple the scaling and alerting decision mechanism from rest of cloud management.

Certain example embodiments provide for users to write complex scaling alerting queries by combining scaling alerting expressions using conditional operators. Another feature of certain embodiments is that the users can change the scaling alerting query without any process restart.

Communication layer provides an interface for communication between scaling master and the plurality of scaling agents . The interface provides for controlling connections and for querying alerting.

Each scaling agent receives scaling and or alerting queries from scaling master through communication layer executes the queries on the corresponding processing element s and returns results to scaling master again through communication layer .

Certain example embodiments allow for decoupled scaling and or alerting decisions to be made using a query. This allows the user to change the scaling alerting condition by modifying the query without any need to restart the agent or a master .

Connection layer is a communication mechanism between scaling master and scaling agent. Connection layer has certain set of interfaces which can be implemented by developers for customization.

Connection layer provides a way to make a connection to agent with given set of connection properties and execute schedule or stop a query on the connection instance. Connection layer may require request listener to be implemented by agent for receiving query policy requests.

The response of a query that is executed once is received via callback. In the case of a scheduled query the compile time error if any is received via callback and result s are streamed to the master. Connection requests for scheduling the queries based on a cron expression.

The implementation of result stream may in some instances be based on a distributed cache implementation such as a Terracotta Server Array. See for example U.S. Publication No. 2012 0222005 the entire contents of which are hereby incorporated herein by reference.

Communication layer provides for scaling master and scaling agent s to communicate with each other using a structured query language. According to certain example embodiments communication layer operates in accordance with a query language referred to as Scaling Query Language or SCQL defined by the inventors. SCQL is a structured query language which represents a scaling alerting condition either by a single scaling alerting expression or by two or more scaling alerting expressions grouped by a conditional operator. Example conditional operators include AND and OR. An appendix setting forth an example application programming interface API for SCQL is included at the end of this specification and before the claims.

According to certain SCQL embodiments a scaling alerting expression completely defines the metric and it s relation to threshold value. An expression is the basic unit which is evaluated by the scaling runtime.

A system level expression represents a metric condition to be computed for a system. Query example 1 instructs a node to vote for a scale down when its average system CPU usage is less than 56 percent for a duration of 10 seconds 

Query example 2 shows an alternative way of specifying metric source parameters inside a properties file. By specifying them in a properties file complex queries may appear less cluttered and more understandable.

An application level expression represents a metric condition to be computed for an application. Query example 3 shows instructs a node to vote for a scale up when application named CricketInfo running on it has average user requests fetched from a web service exceeding 100 for a quantum of 25 metric values.

Another application expression is shown in Query Example 4 which instructs a node to vote for a scale up when an application named EventProcessor running on it has an average queue size fetched from a messaging provider greater than or equal to 55 for a duration of 20 seconds.

A complex scaling query is shown in Query Example 5 which instructs a node to vote for a scale up when maximum of system memory usage values collected for 20 seconds exceeds 200 MB and minimum of 25 responsiveness entries of application named xBay reaches 2 or less.

A complex scaling query is shown in Query Example 6 which instructs a node to vote for a scale up when either average of system memory recorded for 20 seconds greater than 500 MB or average of 25 requests for an application named TestApp exceeds 100 and average system CPU load recorded for 10 seconds exceeds 15.5 .

Query Examples 7 9 illustrates alerting queries. Query Example 7 instructs a node to issue a critical alert when an average system CPU usage is greater than 95 for a duration of 60 seconds.

Query Example 8 instructs a node to issue a warning alert when average of 25 user requests fetched from a web service exceeds 80 for an application named CricketInfo running on it.

Query Example 9 instructs a node to issue a warning alert when average of 50 MyMetric fetched from a custom metric source exceeds 20 for an application named TestApp running on it.

In certain example embodiments scaling and or alerting policies may be defined. A scaling policy or a file contains scale up and or scale down condition per node instance. Different scaling conditions may be provided for different nodes instances in some cases. illustrates an example policy file in accordance with certain example embodiments.

An alerting policy or a file may contain an alert condition per node instance. Different alert conditions may sometimes be provided for different nodes instances in some cases. illustrates an example policy file for alerts in accordance with certain example embodiments.

Scaling master triggers scaling and or alerting computation on each of the configured nodes instances. In the case of scaling queries or a policy the scaling master sums up the query results based on a summation policy and if the conclusion is to scale down it returns the list of the nodes instances to be scaled down based on an eviction policy along with the concluded result.

The summation may be in accordance with a voting scheme. In certain example embodiments the default summation policy or algorithm is fair voting and majority wins in that for example it counts the number of scale up votes and scale down votes and greater of the two majority is the concluded result.

A default eviction policy or algorithm may first calculate the number of nodes say n to be scaled down in order to maintain a desired load by taking into account computed average load. The nodes are ranked among their peers based on weighted average load and finally evicting the least n ranked nodes. For instance 

Custom summation and or eviction policy algorithms can be plugged in by implementing certain interfaces and setting them in a file such as for example the master configuration file.

Scaling master components connect to scaling agent using SCQL connection layer executes schedules queries on it etc. In the case of scaling queries policy it collects and concludes the query results based on summation policy. Also if the conclusion is a scale down it provides back the list of nodes to be scaled down based on eviction policy.

In the case of scheduling a query the scaling master gets the handle to a stream structure such as SCQLResultStream. It may then wait for callback invocation to check if query execution is successful. If successful it then waits for result data to be available in the stream and then fetch the results available from the stream in a waited loop until a job is completed or query has been stopped. The scaling master also has a flow control and feedback control mechanism e.g. FAXLCM described below for scheduled queries.

Given a scenario where a scaling query is to be scheduled on a node e.g. Node A to run for every x minutes the scaling master can ensure that it provides controlled scaling decision s .

For addressing scenarios such as those discussed above the scaling master may include a closed loop flow control mechanism or an open loop flow control mechanism. The inventors have configured an example component referred to as FAXLCM Flow And X Loop Control Mechanism X represents the mode of operation in this regard. FAXLCM may be operated as either a closed loop or an open loop system.

A closed loop control system forms the decision to scale up down or to defer discard it in a way to minimize the deviation between desired metric value and average of measured metric value s . An example closed loop flow and loop control system is shown in . The output of a scaling decision is provided as input to a provisioning system . Provisioning system implements the scaling decision in a system. The output of provisioning system is provided in a result stream . The result stream may be observed to determine the effect of the scaling decision. Basically a provisioning system an external component is the capability of a cloud management platform to provision adds into the topology and decommission removes a virtual machine instance or a computation node from the topology. So the output of provisioning system results in the change in topology for example increase or decrease in the number of web servers hosting an application and hence the changes in load distribution patterns whose effect can be observed in result stream.

The result stream may be used to measure metrics. A flow control determines one or more measured metrics from the result stream at certain intervals. The measured metrics are then compared with the desired metrics and the result of the comparison is provided to the scaling decision operation . According to certain example embodiments scaling decision operation makes a scaling decision based on input including the difference between the desired metric and measured metric.

An open loop control system may use measured variables like threshold value rather than feedback information to make a decision. The decision to report scale up down or to discard defer it is based on threshold period or cool off period.

Scaling master shown in illustrates an FAXLCM operating in open loop mode in accordance with an embodiment. FAXLCM receives a stream of information every x minutes in the form of query results from query scheduling and execution which receives as input queries or a query policy file . A flow control aspect of FAXLCM collects the latest available n entries in intervals and sends them to a summation policy to conclude the query result e.g. a scale down or a scale up . A cool off period may become active after each scaling conclusion is drawn.

Within the cool off or threshold period any scaling decisions made may be discarded or deferred . This may be necessary to avoid undesirable scaling up down of the system.

The cool off or threshold period is time for the system to reach from an oscillating state caused due to scale up down to the point of equilibrium.

According to certain example embodiments the threshold period is set by summing the following amount of time required to provision decommission instance amount of time required to distribute load among new set of nodes and amount of time required to see the effect of load sharing on Node A s metric.

Summing policy outputs a scale up decision or a scale down decision . If a scale down decision is made then a list of nodes to scale down may also be generated by scaling master.

The query received is then compiled by the SCQL compiler and either submitted to the runtime directly for execution or to a scheduler first which then requests the runtime based on a configured cron expression.

The result of the query that is executed is returned back to the master via SCQL callback whereas the scheduled query results are streamed via SCQL result stream.

Scaling agent returns the unique identifier for scheduled query to scaling master as a success response. The master can later request that the query stop using this identifier. SCQL compiler may perform lexical and syntax analysis prior to compiling. In certain example embodiments ANTLR runtime is included in SCQL compiler for performing lexical analysis. AST is then transformed into an XML by semantic analyzer and this XML is converted into a composite by a code generator. The composite which contains scaling expressions grouped by conditional operator is a final form of the compiled query that is executed by a SCQL Runtime .

Composite evaluator which is a component of SCQL runtime understands the expression and translates it into event processing language and submits it to event processor. Composite evaluator listens to CEP statement state change notifications whose data provides expression result. The expression result may be logically e.g. AND OR compared to another expression s result which is at the same level and moves up until final result is extracted. Once the final result is available call back is issued to the master by the agent as per SCQL connection specification.

In the case of scheduled query the scaling agent registers the compiled query against a unique identifier and submits it to the scheduler . The scheduler understands the given cron expression and schedules the compiled query into a job the job run as per cron configuration. The job periodically initializes the runtime composite evaluator and streams the query results into SCQLResultStream .

IF case a scheduled job is completed scaling agent sets the status of stream parameters as seen by scaling master such that for example job completed true data available in stream false etc.

If a runtime error occurs the agent injects the error into the stream to be retrieved by master and act accordingly and scaling agent also set the status of job completed parameter to true.

In case scaling agent receives the request to stop the query scaling agent checks if provided query id is valid. If the id is valid then de register the query and cancel the scheduler job running. It has the same effect as job completion as seen by master.

Method illustrates communication between the scaling master scaling agents and the connection layer. Operations illustrated in the column are those performed by scaling master operations in are performed by scaling agents and those in are performed by the connection layer.

After entering the method at the scaling master is initialized with a given configuration file at . The configuration file may include connection information for the scaling agents. The configuration file may also include one or more user specified queries such as for example any of the query examples discussed above.

At operation a driver for communicating using the connection layer is initialized for the scaling master.

At operation the scaling master connects to one or more scaling agents based on the connection properties of the agents and the required connection properties as set forth in the corresponding entries in the configuration file.

Also at operation a scaling and or alerting query is transmitted to the connected one or more agents. At this time scaling agents are listening at operation for incoming query requests. The connection between master and agent s is provided by the connecting layer . For example the connecting layer initializes a driver e.g. SCQL driver and creates the SCQL connection for use for communication between the scaling master and agents.

At operation a callback is implemented and initialized for receiving the results of the query. At operation it is determined whether the query is scheduled for future execution or being executed immediately.

If the query is to be scheduled then at operation the query is scheduled and a call back is registered at the connection instance. At the scaling master waits for the responses to the query via call back media.

If the results received at include errors as determined by operation then the processing at the scaling master stops.

If on the other hand at it was decided not to schedule the query then method proceeds to . At operation a call back is registered and the query is executed on the connection instance.

If on the other hand at it was determined that no errors were present then method proceeds to operation . At operation the scaling master waits for query results to be available in a result stream.

At operation the results in the stream are looped through until the job is completed or query is stopped.

Operation illustrates requesting agent to stop the query given the query identifier obtained when the query was implemented at the agent.

At the agent after the listener detected the SCQL connection at and received the query and or policy from the master at operation the query is subjected to lexical syntax and semantic analysis before being compiled and code generated at .

At operation it is determined whether the query is to be scheduled. If yes at operation the query is registered and submitted to the scheduler.

At operation the SCQL runtime is initialized. Composite evaluator with input from metric source and event processing execute the query. The query result is prepared at operation .

At operation it is determined either that the result is to be forwarded to the stream or that the result is to be provided to the master via the callback .

The description above with respect to method illustrates communication between the scaling master scaling agents and the connection layer.

A description of certain terms is provided below for aiding in the understanding of how certain example embodiments may operate. However it is to be understood that the following descriptions are provided by way of example for explanatory purposes and should not be construed as being limiting on the claims unless expressly noted.

It will be appreciated that as used herein the terms system subsystem service engine module programmed logic circuitry and the like may be implemented as any suitable combination of software hardware firmware and or the like. It also will be appreciated that the storage locations herein may be any suitable combination of disk drive devices memory locations solid state drives CD ROMs DVDs tape backups storage area network SAN systems and or any other appropriate tangible non transitory computer readable storage medium. Cloud and or distributed storage e.g. using file sharing means for instance also may be used in certain example embodiments. It also will be appreciated that the techniques described herein may be accomplished by having at least one processor execute instructions that may be tangibly stored on a non transitory computer readable storage medium.

While the invention has been described in connection with what is presently considered to be the most practical and preferred embodiment it is to be understood that the invention is not to be limited to the disclosed embodiment but on the contrary is intended to cover various modifications and equivalent arrangements included within the spirit and scope of the appended claims.

