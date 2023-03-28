# Spring---MVC-Framework

## The main components of Spring MVC framework are:

- Model: This component represents the data and business logic of the application. It contains data that is used by the application and provides methods for manipulating that data.

- View: This component is responsible for presenting the data to the user. It generates the user interface and displays the data from the model.

- Controller: This component is responsible for handling user requests, processing user input, and updating the model and view accordingly. It acts as an intermediary between the model and view components.

## Spring MVC architecture

1. dispatch-servlet->
nothing but web.xml.
The Spring Web model-view-controller (MVC) framework is designed around a Dispatcher Servlet that handles all the HTTP requests and responses. --this is the front controller or servlet and it is responsible to handle internal application flow(hit to web.xml)

2. HandlerMapping:
After receiving an HTTP request, DispatcherServlet consults the HandlerMapping to call the appropriate Controller. to find the controller specified (mapping in spring-servlet.xml)

<beans xsd>	based-package = com.app.controller

a) scan in controller above code and again going to Handler Mapping-->dispatch-servlet

3. dispatch-servlet->
The Controller takes the request and calls the appropriate service methods based on the used GET or POST method. The service method will set model data based on defined business logic and returns view name to the DispatcherServlet.

4. handler adaptor:
handlerintersafter (working is databinding, validation, conversion, formatting, Invoke service, update model and state) two type of request process
1)	Pre and post 

5. Controller -> read the method or scan the method and execute   --> view name -> nothing but which page to redirect 
	if over project is MVC pattern before 6 step this 3 steps fallows
	a)service
	b) repository
	c) Database
6. handler adaptor:
spring-servlet.xml in this handler adapter mapping provided and mapping view Resolver.

7. dispatch-servlet->
processingThe DispatcherServlet will take help from ViewResolver to pick up the defined view for the request

8. view Resolver: 
it is responsible to handle the request pages
	by using: prefix: /web-inf/view/	suffix: .jsp
a) model: POJO, bean, setter/getter, entity, domain

9. view
(response)Once the view is finalized, The DispatcherServlet passes the model data to the view which is finally rendered on the browser.
web-inf/ madhespring-servlet.xml and web.xml

![image](https://user-images.githubusercontent.com/73180409/228178042-dbaca302-53a0-4258-84df-566b21aa99b0.png)
