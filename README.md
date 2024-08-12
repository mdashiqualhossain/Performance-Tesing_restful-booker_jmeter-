# Performance Testing
This repository contains performance testing documentation to evaluate the performance of the Restful Booker API hosted on restful-booker.herokuapp.com. The tests are conducted using Apache JMeter, a powerful open-source tool for performance testing.
## Install
JAVA

https://www.oracle.com/java/technologies/downloads/

JMeter

https://jmeter.apache.org/download_jmeter.cgi

## Collection of API

A set of API for restful-booker.herokuapp.com is utilized, which includes various HTTP methods such as POST, GET, DELETE, and PUT.

## Load Testing

## Test Plan
Test Plan > Add > Threads (Users) > Thread Group

Name: Users

Number of Threads (Users): 

Ramp-up Periods (in Seconds):

Loop Count: 1


1. Test Plan specifies the general settings for test execution, such as whether Thread Groups will run simultaneously or sequentially.
2. HTTP Requests utilize some of the HTTP Request item's default settings, such as the Server IP, Port Number, and Content-Encoding.
3. Each Thread Group describes how HTTP requests should be executed. To establish how many concurrent "users" will be simulated, we first need to determine the number of threads. The loop count determines the number of actions that each "user" will perform.
4. The first item in Thread Groups is the HTTP Header Manager, which lets you input the Request Headers that the next HTTP Requests will use.

## Using User Defined Variables Steps:

1.Right-click on the Test Plan or any other node in your test plan.
2.Go to Add > Config Element > User Defined Variables.
3.In the User Defined Variables configuration, add the variable name and value.
Example:
If you add a variable called baseUrl with a value of https://restful-booker.herokuapp.com/, you can use this variable in your test plan by referencing it as ${Url}.

![image](https://github.com/user-attachments/assets/e4462ca1-d4bd-4ee0-aef0-18000acb9a40)

## JSON Extractor in JMeter: Quick Steps
1.Add HTTP Request: Create an HTTP Request in your test plan.
2.Add JSON Extractor: Right-click the HTTP Request, then add Post Processors > JSON Extractor.
Configure:
Variable Name: e.g., bookingId.
JSON Path: e.g., $.bookingid.

![image](https://github.com/user-attachments/assets/2aef1cc0-5b90-4e9e-8076-0cd38f136dff)




## First Thread Group


Number of Threads: 700

Ramp-up Period:10

![image](https://github.com/user-attachments/assets/e92ee68d-5a0f-42cf-9b4f-14f10a1339e3)
![image](https://github.com/user-attachments/assets/7ac69fe0-ce95-47ae-a7fe-6a536f4e135a)




## Second Thread Group

Number of Threads: 800

Ramp-up Period: 10



![image](https://github.com/user-attachments/assets/8eb5107f-a5b2-4929-b1ad-961f09589f02)
![image](https://github.com/user-attachments/assets/16736bc9-04b1-481b-8282-df5e84a0917e)



## Summary 

While executed 100 Threads, a total of 600 concurrent request are made found with error rate 0%

While executed 1600 Threads, a total of 9600 concurrent request are made found with error rate 0%

While executed 2500 Threads, a total of 15000 concurrent request are made found with error rate 0.02%


Server can handle almost concurrent 2500 API call with almost zero error rate.




