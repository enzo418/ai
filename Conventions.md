# Conventions

## Stack

* .NET 8, C#, Entity Framework Core
* React + TypeScript on the frontend

## Patterns

* Services → Interfaces → Repositories, never direct access
* Errors: `Result<T>` pattern, no exceptions for flow control
* `async/await` throughout the entire chain, never `.Result` or `.Wait()`

## Naming

* Interfaces: `IFooService`
* DTOs: `FooRequestDto` / `FooResponseDto`
* Tests: `MethodBeingTested_Scenario_ExpectedResult`

## What we do NOT do

* No business logic in controllers
* No direct queries in services; they belong in repositories
* No magic strings; everything goes in constants or enums

## Communication

* Use the same language to communicate between system (DTO/Contracts/Interfaces) an use propper mapping
* Use a consistent error format between user-facing system and backend. 

## Log

* Don't overlog
* Can it be solved by engineering -> Log Error.
* It's a external error (e.g. provider, client config) that impairs the flow -> Warning
