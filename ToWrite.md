# Topics that I should write about

## When to create a library?

When you write software you are generally trying to deliver some service to end users and you are likely to achieve this through deployment of a set of micro services which provide the end user service.

As you create the microservices you have a constantly consider if the code you write is specific to one service or would be better split out into a library.

There is a cost to create a library in terms of
- creating a new project
- thinking about the functionalty in a generic way
- adding to CI
- describing the functionality so it can be consumed in the future
You dont pay this 'libraritization' cost if you leave the functionality within an micro service project.


When do you make the decision that splitting some functionality out into a library has a benefit that exceeds the cost?

 
## Why open source a library?

In order to open source functionality it is likely there will be objections to overcome including:
- it our customers ip
- its our know how even if not our IP
- why not just keep it private, its safer