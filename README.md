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
is getting called , traceid ( unique id along the entire request , same for all the services ) , spanid ( one span id for each and every service) and export details.
 
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


