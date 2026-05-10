# Conventions

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
* Do not log messages with variable data on the message, use structured loggin.
* Use event wide logging

## Testing

* Use unit testing when possible
* Test a few good examples, only if needed can also validate a negative case.
