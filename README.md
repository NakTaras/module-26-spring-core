# module-26-spring-core

## Self-study materials
Please, look through the following materials:

### Lectures:

- [Spring core](https://www.linkedin.com/learning/spring-framework-in-depth-2)
- [New in Spring 5.0](https://learn.epam.com/detailsPage?id=1a5d6b23-b4b9-4942-bf64-a8e758d3ef01%C2%A0)
- [Testing](https://learn.epam.com/detailsPage?id=4e3bf752-9800-4cd1-a36f-34bf61799ad8%C2%A0)

### Books

- Spring in Action, Fifth Edition (Craig Walls)
- Spring in Practice (Willie Wheeler, Joshua White)
- Pro Spring (Harrop Rob, Ho Clarence)
- Getting started with Spring Framework: a hands-on guide to begin developing applications using Spring Framework 3rd Edition (J Sharma, Ashish Sarin)
- Just Spring: A Lightweight Introduction to the Spring Framework (Madhusudhan Konda)

### Sites:

- [Core Technologies](https://docs.spring.io/spring/docs/current/spring-framework-reference/core.html#spring-core)
- [Inversion of Control and Dependency Injection](https://martinfowler.com/articles/injection.html_)
- [Testing](https://docs.spring.io/spring/docs/current/spring-framework-reference/testing.html#testing)
- [Logging](https://docs.spring.io/spring/docs/5.0.0.RC3/spring-framework-reference/overview.html#overview-logging)
- [Logging tutorial](https://www.tutorialspoint.com/spring/logging_with_log4j.htm)

## Task
Please, complete the following task.

<b>The total mark is 7:  5 points for regular homework and 2 points for the extra mile. </b>


<b>Create a Spring-based module, which handles event ticket booking. </b>

Based on the attached source code model:

1. Implement three service classes:

- UserService

- EventService

- Ticket service

which should contain user, event, and booking-related functionality accordingly. Create an implementation of the BookingFacade interface which should delegate method calls to services mentioned above.

<b>(0.5 point)</b>

2. Configure spring application context based on the XML config file. <b>(0.5 point)</b>

3. Implement DAO objects for each of the domain model entities (User, Event, Ticket). They should store in and retrieve data from a common in-memory storage - java map. Each entity should be stored under a separate namespace, so you could list particular entity types. <b>(0.5 point)</b>

Example for ticket - map entry {"ticket:" à {}}.

E.g. {"ticket:12345" à {"id" : 12345, "place" : 23, ......}}

4. Storage should be implemented as a separate spring bean. Implement the ability to initialize storage with some prepared data from the file during the application start (use spring bean post-processing features). Path to the concrete file should be set using property placeholder and external property file. <b>(1 point)</b>

5. DAO with storage bean should be inserted into services beans using auto wiring. Services beans should be injected into the facade using constructor-based injections. The rest of the injections should be done in a setter-based way. <b>(1 point)</b>

6. Cover code with unit tests. <b>(0.5 point)</b>

7. Code should contain proper logging. <b>(0.5 point)</b>

8. Create several integration tests that instantiate the Application Context directly, lookup facade bean and perform some real-life scenario (e.g. create user, then create event, then book ticket for this event for the user, then cancel it). <b>(0.5 point)</b>

### Extramile:


<b>2 points</b>

Use "p" namespace to define properties Use SLF4J API for logging, configure Spring to use SLF4J, and add some Spring logging output to the common application log. 