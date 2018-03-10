![Manga](https://raw.githubusercontent.com/ivanpaulovich/manga/master/docs/manga-icon.png) Caju: Back-end with awesome architectures made easy!
=========
<a href="https://www.nuget.org/packages/Paulovich.Caju/" rel="Paulovich.Caju">![NuGet](https://img.shields.io/nuget/v/Paulovich.Caju.svg)</a> [![Build Status](https://travis-ci.org/ivanpaulovich/caju.svg?branch=master)](https://travis-ci.org/ivanpaulovich/caju)

Caju is a Service Template for helping you to build evolvable, adaptable and maintainable applications. It follows the principles from the [Clean Architecture book](https://www.amazon.com/Clean-Architecture-Craftsmans-Software-Structure/dp/0134494164) and has a Domain built on Domain-Driven Design. It is easy for you to start your new microservice based on its guidelines and patterns.

## Generate your own awesome Back-end!

To create a dotnet application based on this template:

```sh
dotnet new -i Paulovich.Caju
dotnet new caju -n "MyProject"
```

## The Clean Architecture

The implementation result of the Clean Architecture is a software that encapsulate Business Rules in Use Cases and the Enterprise Rules in Entities. Also the Use Cases are independent from details like User Interface, Data Access, Web Server or any external agency. 

![Clean Architecture by Uncle Bob](https://raw.githubusercontent.com/ivanpaulovich/manga/master/docs/CleanArchitecture-Uncle-Bob.jpg)
> The Clean Architecture Diagram by [Uncle Bob](https://8thlight.com/blog/uncle-bob/2012/08/13/the-clean-architecture.html).

| Concept | Description |
| --- | --- |
| DDD | The Use Cases of the Account Balance are the Ubiquitious Language designed in the Domain and Application layers, we use the Eric Evans terms like Entities, Value Object, Aggregates Root and Bounded Context. |
| TDD | From the beginning of the project we developed Unit Tests that helped us to enforce the business rules and to create an application that prevents bugs intead of finding them. We also have more sophisticated tests like Use Case Tests, Mapping Tests and Integration Tests. |
| SOLID | The SOLID principles are all over the the solution. The knowledge of SOLID is not a prerequisite but it is highly recommended. |
| Entity-Boundary-Interactor (EBI) | The goal of EBI architecture is to produce a software implementation agnostic to technology, framework, or database. The result is focus on  use cases and input/output. |
| Microservice | We designed the software around the Business Domain, having Continous Delivery and Independent Deployment. |
| Logging | Logging is a detail. We plugged Serilog and configured it to redirect every log message to the file system. |
| Docker | Docker is a detail. It was implemented to help us make a faster and reliable deployment. |
| MongoDB | MongoDB is a detail. You could create new Data Access implementation and setup it with Autofac. |
| .NET Core 2.0 | .NET Core is a detail. Almost everything in this code base could be ported to other versions. |

## Sample applications

Run `dotnet new -i Paulovich.Caju` then try the following commands.

Solution with all use cases:

```sh
dotnet new caju \
	--name "MyFullProject"
```

Basic application with Register Customer and Get Customer Details use case:

```sh
dotnet new caju \
	--use-cases basic \
	--name "MyBasicProject"
```

Empty application with the fundamental structure and components only:

```sh
dotnet new caju \
	--use-cases empty \
	--name "MyEmptyProject"
```

## Roadmap

* **Architecture Style**: allow to choose between *Clean Architecture* :white_check_mark:, *Hexagonal Architecture* and *Event-Sourcing*.
* **Use Cases**: allow to choose between predefined Use Case sets *Full* :white_check_mark:, *Basic* :white_check_mark:, *Read Only* :white_check_mark: and *Empty* :white_check_mark:.	
* **Infrastructure**: allow to choose infrastructure implementations like *MongoDB*, *Kafka* or *SQL-Server*.
* **UI**: allow to choose UI implementations like *WebAPI* or *Console* or *Both* or *None*.
* **Skip Restore**: enable or disable the `dotnet restore` after code generation. :white_check_mark:
* **Documentation**: enable or disable documentation tips. :white_check_mark:
