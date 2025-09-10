# Experiences with Claude
## Use-case 1 - Claude based refactoring
Application: Hermes - Occasional Point of Sales

Java version: 21, freshly migrated from Java 8

Framework: Spring Boot 3.5

### Why refactor:
Untested Spaghetti Ball-of-Mud to clean organisation with tests.

### Goal:
#### Using FERV Architecture 
(This might already have another name somewhere on the internet)

Flows, Encapsulated Rich Verticals meaning Rich objects, organisation not by type of class(Controller, Service) but by domain object and its flows

Rich domain objects, that can also serve as Database entities.
Specific models for in- and output.
```text
An excerpt layout of code

src/main/.../hermes
|- flows
||- orders
|||- PlaceOrder
||- accounts
|||- RegisterAccount
|\- tables
```

This resembles DDD, Clean Architecture, ... on some points, but is better suited for small-ish projects

#### Contract-driven testing
have tests that run the full stack in most of the tests. While test startup time is a bit slower, it guarantees a constant testing of the entire application.


### Modus Operandus
After `/init`-ing claude, prompts are usually in the system of `Using some pre-existing set of code, generate me the code to do X or Y`. eg: create new openApi spec block, add tests for all the cases that were specified, and then generate the code to do so.
Depending on the size of the changes, request permission to do the changes.

#### Result after a few prompts
I feel like a cheater. The generated code is not _exactly_ what I would write, but close enough. It uses example code and nicely emulates it in following generations, both in naming conventions and in code setup and building.
It does have the tendency to overengineer, and you need to hold its hand a bit.
It is, however, exceedingly simple to rollback changes that went too far, or where you've missed something in the prompt.
