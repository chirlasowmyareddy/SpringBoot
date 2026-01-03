Servlet
    - provide foundation for building web applications
    - Servlet is a Java class, which handles client request,process it and return the response
Servlet Containers
    - These are the ones which manages the Servlets
    - Eg:- Tomcat(Our application is deployed here)
    - this COntainer used web.xml to determine which servlet to invoke

Spring Framework
    - solves challenges which exists with Servlets

    Removal of web.xml
        - this web.xml file over time becomes too big and becomes very difficult to manage and understand
        - spring framework introduces Annotations based configuration
    Inversion of Control(IoC)
        - IoC is more flexible way to manage object dependencies and its lifecycle (through dependency injection)
        - actually dependency injection is an implementation for IoC
    Unit Testing is Much Harder
        - As the object creation depends on the servlet ,mocking is not easy.Which makes unit testing harder
        - Spring dependency injection facility makes the Unit testing very easy.
         - by using @Autowired the spirng itself manages the object creations
    Difficult to Manage Rest API's
        - Handling different HTTP methods,request parameters,path mapping make code little difficult to understand.
        - Spring MVC provides an organised approach to handle the requests and its easy to build RESTful API's.

How Spring MvC works
    The request will reach the servlet container(tomcat) then the dispatcher servlet chooses the controller by using HandlerMapping which checks the mapping requests and create an instance of controller which uses IoC(Initiate an instance of the controller along with its dependencies if any means injects any depencies by creating objects)
    and then invokes controller methods where respective api gets invoked and returns the response
    (or)
    When a request comes in, it first reaches the servlet container (Tomcat), which forwards it to the DispatcherServlet. The DispatcherServlet acts as the front controller and uses HandlerMapping to identify the appropriate controller method. The controller bean is already created by Spring using IoC and dependency injection at startup. The DispatcherServlet then uses a HandlerAdapter to invoke the controller method, where the corresponding API logic is executed. The response is processed using HttpMessageConverters to convert it into JSON or XML, and finally, the response is sent back to the client via Tomcat.
Spring Boot
    Depedency Management 
        - No need for adding different dependecies separately and also their compatible version headache
    Auto-configuration
        -  No need for separately configuring "Dispatcher Servlet","App config","EnableWebMvc","ComponentScan".Spring boot add internally by default
    Embedded Server
        - In traditional Spring MVC application, we need to build a WAR file,which is a packaged file containing your application's classes,JSP pages,config files,and dependencies
        Then we need to deploy this WAR file to a servlet container like tomcat

        But in spring boot ,Servlet container is already embedded ,we don't have to do all the stuff.just run the application that's all.

What is Spring Boot?
    - It provided a quick way to create a production ready application
    - It is based on spring framework
    - It support "Convention over Configuration"
        - uses default values for configurations, and if developer don't want to go with convention(the way something is done),they can override it
    - It also help to run the application as quick as possible