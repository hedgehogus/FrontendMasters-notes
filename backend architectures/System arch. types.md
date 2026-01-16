## Three commonly used architectures
- monolithic
- distributed (service-oriented)
- serverless

## Monolithic
**definition** - monolithic architecture is a model where all the necessary code and components for a software application are combined into a single unit.   
   
Has all fucntionalities tightly coupled, running in the same system.  
    
This architecture is simple to develop, test, and deploy due to its unified system   

Pros:
- **simplicity**: Easier to develop, test, and deploy due to unified system (good for newhires)
- **consistency**: Allows for uniformity in handling requests as every module uses the same set of procedures
- **efficiency**: Since all the functionalities are interconnected, it can be more efficient in terms of inter-process communication
      
Cons:
- **limited scalability**: Scaling specific functions of a system is not possible. The entire system needs to be scaled
- **lack of flexibility**: changes to a single component can require the entire system to be redeployed
- **complexity**: The system can become too complex and hard to manage as the application grows

Use Cases:
- **small-scale applications**: Given its simplicity, a monolithic architecture is often suitable for small-scale applications or startups where the application's scope is clear and unlikely to drastically change or scale
- **application with simple, well-defined business processes**: Monolithic architecture can be beneficial in scenarios where the business processes are simple and unlikeky to require significant changes or additions.
- **applications where high perfomance is critical**: Since all functionalities are interconnected, a monolithic architecture can provide faster inter-process communication compared to other architectures

## Distributed Architectures
Generic services and/or microservices archotecture is a method of developing software systems that are loosely coupled and independently deployable smaller services, which run in their own processes.     
    
This architecture allows for continuous delivery and deployment of large, complex applications. It also enhances an organization's capability to innovate and reduces the time to market for new features.    

### Generic Services
**Generic services** often refers to a component of an application that provides specific functionality for the platform    
    
Generic services could be part of monolithic application where all services run within the same process, or it could be part of a distributed system where services may run in separate processes or on separate machines 


