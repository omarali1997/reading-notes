# read 13: Serverless Functions
># Serverless Functions
### Serverless is a deployment architecture where servers are not explicitly provisioned by the deployer. Code is instead executed based on developer-defined events that are triggered, for example when an HTTP POST request is sent to an API a new line written to a file.


## How can code be executed "without" servers?

### Servers still exist to execute the code but they are abstracted away from the developer and handled by a compute platform such as Amazon Web Services Lambda or Google Cloud Functions.


<img src="https://www.fullstackpython.com/img/visuals/serverless.png" />

### Think about deploying code as a spectrum, where on one side you build your own server from components, hook it up to the internet with a static IP address, connect the IP address to DNS and start serving requests. The hardware, operating system, web server, WSGI server, etc are all completely controlled by you. On the opposite side of the spectrum are serverless compute platforms that take Python code and execute it without you ever touching hardware or even knowing what operating system it runs on.

### In between those extremes are levels that remove the need to worry about hardware (virtual private servers), up through removing concerns about web servers (platforms-as-a-service). Where you fall on the spectrum for your deployment will depend on your own situation. Serverless is simply the newest and most extreme of these deployment models so it is up to you as to how much complexity you want to take on with the deployment versus your control over each aspect of the hardware and software.

## Serverless implementations

### Each major cloud vendor has a serverless compute implementation. These implementations are under significant active development and not all of them have Python support.

* ### AWS Lambda is the current leader among serverless compute implementations. It has support for Python 3.x.
* ### Azure Functions has second-class citizen support for Python. It's supposed to be possible but kind of hacky at the moment. Polyglot support should be quickly coming to Azure to better compete with AWS Lambda.
* ### IBM Bluemix OpenWhisk is based on the Apache OpenWhisk open source project.

* ### Google Cloud Functions has native Python 3.x runtimes.

* ### Webtask.io started as a JavaScript service but now also has a Python runtime as well.

## Serverless frameworks

### Serverless libraries and frameworks aim to provide reusable code that handles common or tedious tasks, similar to how web frameworks deal with common web development tasks. Some of these frameworks are built for a single service like AWS Lambda, while others attempt to make cross-serverless operations more palatable.

## Frameworks for building Python-based applications on serverless services include:

* ### Serverless (source code), which is a useful but generically-named library that focuses on deployment and operations for serverless applications.

* ### Zappa provides code and tools to make it much easier to build on AWS Lambda and AWS API Gateway than rolling your own on the bare services.

* ### Chalice (source code) is built by the AWS team specifically for Python applications.




