```
Services
ServiceRegistry
Log Tracing
API Gateway
Hytsrix
```

<img width="727" alt="Screenshot 2023-01-12 at 11 59 02 PM" src="https://user-images.githubusercontent.com/43849911/212149270-ade68bba-b479-4e6b-b2ec-8ad40c0a36fc.png">

```
All the microservices will be connected to the service registry, 
so that we call get an idea about what all the microservices
available and the status of all the microservices.

All the requests will be sent to API Gateway first then they are
forwarded to corresponding services via url reference or pattern. 

Using timeout , we can check whether a particular service is working 
or not. A fallback method will be triggered in case the response is
not generated in a given time frame doesn't work.

Using Hystrix Circuit Breaker we can visualise how much the api
endpoints are failing and how much are getting successful. And 
which microservice is not working.

Repeated configurations can be placed at config service as it is
not a best practice to include them at all the services.

Distributed logging can be to identify which microservice is getting 
failed and where the request is traversing.

For this , we can make use of sleuth and zipkin server , zipkin client at the services.

Sleuth provides multiple flags like service id using which we can identify which of the services
is getting called , traceid ( unique id along the entire request , same for all the services ) , spanid ( one span id for each and every service) and export flag.
 
For centralised logging frameframework we can also implement elk stack
```

```
For 2 microservices we can easily make api calls but when there are multiple microservices
exchanging info. b/w them becomes difficult . And also scaling will not be so easy.
```

```
We can create a service registry and it will maintain all the endpoints for it. It will have information about all the microservices including their status updated , url info. and port no.
```

```
Requests will come to API Gateway first and based on url pattern , they will be traversed.
```

```
application.yml can be used for the ApplicationContext . Whenever the application starts, spring boot will make use of this file.
```

https://zipkin.io/pages/quickstart

```
curl -sSL https://zipkin.io/quickstart.sh | bash -s
java -jar zipkin.jar
```

<img width="1789" alt="Screenshot 2023-01-17 at 1 50 52 AM" src="https://user-images.githubusercontent.com/43849911/212759818-e7c37481-6a6a-4d81-81f7-c3463fc4ed6c.png">

<img width="599" alt="Screenshot 2023-01-17 at 1 52 50 AM" src="https://user-images.githubusercontent.com/43849911/212760106-22ca8ca1-207f-417a-a446-3ba3d16321cf.png">

<img width="1078" alt="Screenshot 2023-01-17 at 1 54 08 AM" src="https://user-images.githubusercontent.com/43849911/212760299-6f21cc11-27a0-4326-9cd8-86c7c050e02f.png">

<img width="1519" alt="Screenshot 2023-01-17 at 1 55 58 AM" src="https://user-images.githubusercontent.com/43849911/212760510-e60e44af-88d5-4cf7-862e-51becd78c0a3.png">

<img width="1020" alt="Screenshot 2023-01-17 at 2 02 59 AM" src="https://user-images.githubusercontent.com/43849911/212761443-f7d14a04-fd88-4c8f-8be8-feb81e150573.png">

<img width="1792" alt="Screenshot 2023-01-17 at 2 10 09 AM" src="https://user-images.githubusercontent.com/43849911/212762318-4390dd27-bd2d-47b0-81c7-3f7f86e5edd0.png">

<img width="1792" alt="Screenshot 2023-01-17 at 2 11 19 AM" src="https://user-images.githubusercontent.com/43849911/212762444-20d68819-53a2-4e5d-b22c-00e0eaff6dd9.png">

<img width="1792" alt="Screenshot 2023-01-17 at 2 12 26 AM" src="https://user-images.githubusercontent.com/43849911/212762603-405abf3e-f66b-42c6-a81d-50210ce52cc9.png">

<img width="1788" alt="Screenshot 2023-01-17 at 2 13 27 AM" src="https://user-images.githubusercontent.com/43849911/212762721-0545c35b-790a-44d5-be53-312c6f43f7c9.png">

```
fallback will trigger when department service doesn't work via hystrix circuit breaker
```

<img width="1787" alt="Screenshot 2023-01-17 at 2 14 54 AM" src="https://user-images.githubusercontent.com/43849911/212762887-bd9cb702-6164-45c9-acbe-bece2a35af13.png">

<img width="1791" alt="Screenshot 2023-01-17 at 2 15 28 AM" src="https://user-images.githubusercontent.com/43849911/212762949-68053d0e-592a-45c4-a5fb-76a45eef2c94.png">

<img width="1781" alt="Screenshot 2023-01-17 at 2 16 09 AM" src="https://user-images.githubusercontent.com/43849911/212763058-1c799330-9120-46ef-a14d-e1a7549cfb3a.png">

<img width="1212" alt="Screenshot 2023-01-17 at 2 18 08 AM" src="https://user-images.githubusercontent.com/43849911/212763374-5b954c51-a4a8-4822-9038-602d0b7deacf.png">

<img width="718" alt="Screenshot 2023-01-17 at 2 19 30 AM" src="https://user-images.githubusercontent.com/43849911/212763582-b9c66e10-aa63-4268-9096-d0ba774f4fc5.png">

<img width="986" alt="Screenshot 2023-01-17 at 2 36 54 AM" src="https://user-images.githubusercontent.com/43849911/212765753-abfd6de7-e524-4c0d-9e9d-f4d160903c20.png">

<img width="1061" alt="Screenshot 2023-01-17 at 2 21 09 AM" src="https://user-images.githubusercontent.com/43849911/212763762-b5de2b45-b168-4fd6-8ce2-66fff69a147b.png">

<img width="895" alt="Screenshot 2023-01-17 at 2 21 35 AM" src="https://user-images.githubusercontent.com/43849911/212763820-5da1da39-e89a-451d-b268-0b84680f1dab.png">

<img width="958" alt="Screenshot 2023-01-17 at 2 34 55 AM" src="https://user-images.githubusercontent.com/43849911/212765503-1ec30fbf-ad67-4719-a182-d14eb98d1567.png">

<img width="1439" alt="Screenshot 2023-01-17 at 2 23 10 AM" src="https://user-images.githubusercontent.com/43849911/212764010-5befab42-0f14-4c4c-8154-55136608e9d6.png">

<img width="1203" alt="Screenshot 2023-01-17 at 2 32 34 AM" src="https://user-images.githubusercontent.com/43849911/212765211-026c20a4-34f9-495a-810e-e1e72490ea34.png">

<img width="1731" alt="Screenshot 2023-01-17 at 2 30 24 AM" src="https://user-images.githubusercontent.com/43849911/212765003-c321807a-622e-41f0-8951-7c50cab2b273.png">
