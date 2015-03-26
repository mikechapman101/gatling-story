BBC Gatling Story
=================

Both the BBC Future Media Load Test Team and various BBC product 
teams use Gatling as a core part of our load testing effort. 

Why Gatling?
-----------

There are three major factors that attracted us to Gatling: 

1. The HTTP DSL
2. The reporting
3. Its concurrency model

### HTTP DSL

There are a number of load-test tools that only allow tests
to be written in the GUI or through XML files. We wanted 
test-scripts that were easily understandable and that could
be committed to a version control system. 

### Reporting

The interactive JavaScript reports that are produced after
the test run are extremely impressive and product teams 
have been keen to receive the reports and analyse the results 
themselves.

The integration with Graphite/InfluxDB and Grafana was also 
key for us as we are now able to provide real-time graphing 
for product teams to view during the test run.  

### Concurrency Model  

With a synchronous concurrency model it is necessary to use  
multiple machines just to achieve several hundred requests per
second. Scaling-out can be tricky to manage and be costly when 
running from The Cloud. We have managed to achieve a high 
concurrency rate with Gatling with one modest GNU/Linux box. 

The Story
----------

Apart from myself there are two other load-testers in the BBC
Future Media Load Test Team who cover an array of application 
services and products. Our two main tools include Gatling 
and a proprietary tool.  

We feel that Gatling encourages collaboration with product 
teams throughout the load-testing process. Firstly, performance 
requirements are written on a wiki, translated into a 
Gatling test script and then pushed to our
[Github repository](https://github.com/bbc/gatling-load-tests).
Here the test is reviewed by a member of the product team. This 
is important because the developers do not need to install a load-test tool
or wade through masses of XML in order to review the test. The 
DSL is understandable by all and invariably changes are requested 
by stakeholders when a concrete test is seen. 

We have created Grafana and InfluxDB Docker images that can be 
[run](https://github.com/bbc/gatling-load-tests#real-time-metrics) 
to receive out-of-the-box real-time graphing and metric storage. 
The allows both ourselves and our product teams to view the progress of 
the test run and use SQL like queries to retrieve data related to 
specific time series data.  

The automatic generated reports are tarballed and uploaded to a server
for stakeholders to access. 

The Future
----------

We are beginning to help product teams run Gatling as part of their
continuous delivery pipeline utilising the 
[Gatling Jenkins plugin](https://wiki.jenkins-ci.org/display/JENKINS/Gatling+Plugin)




