# Spring Boot Architecture

In Spring Web, every controller gets converted to a servlet behind the scenes. 

We are able to run the Spring applications on tomcat because of these servlets. 

In other words we can say all the controllers (servlets) run on a servlet container (tomcat)

Every request, would go through a dispatcher servlet which would decide which method of which controller should be called as per the URI of the request. 

Before dispatcher servlet, the request would go through a chain of filters. The number of types of filters that are present would depend upon how to configure our application. 

## Filters
Filters in Spring Boot allows us to intercept and manipulate http requests and responses. Filters can be used for a variety of purposes including

1. Logging: Capturing request and response details for monitoring
2. Authentication:  Checking user credentials before allowing access to certain resources
3. Input Validation: Validate the input
4. Response Modification: Modify the response before sending it to the client.

### How can we configure Filters
There are two ways in which filters can be configured

1. Using Filter Class: We can create a filter class (A class that extends Filter) and annotate it with @Component to register it automatically as a filter. 
2. Using FilterRegistrationBean: We can use FilterRegistrationBean to configure the order and URL patterns.

### What are the different predefined filters available in spring boot?
1. CharacterEncodingFilter:
  
2. Ensures that the request and response characters are set correctly to UTF-8
   
4. HiddenHttpMethodFilter:

   This is used primarily by spring. Forms support only GET and POST Methods. If the controller contains PUT, we get a 405: Method not supported error. We prevent this error by mentioning the put method URL in a hidden field and this filter takes care of mapping the request to PUT.
    
5. HttpPutFormContentFilter:

6. RequestContextFilter:

   This filter provides access to the RequestContext for the current thread allowing for easier access of request attributes.
   
7. CorsFilter

   Handles Cross Origin Resource Sharing requests allowing and disallowing requests for different domains. 

8. SecurityFilterChain

   Contains a chain of filters for handling the security of the application

9. UsernamePasswordAuthenticationFilter

   This filter is responsible for implementing Spring security by using a user name and password. It extracts the user name and password from the request and authenticates based on them.  
