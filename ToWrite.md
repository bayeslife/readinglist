# Topics that I should write about


## The technique for reading from the Azure Event Hub

The pattern for interacting with Azure Event Hub…read in batches, buffer, retrying indefinitely,  use an offset.

## When to create a library?

When you write software you are generally trying to deliver some service to end users and you are likely to achieve this through deployment of a set of micro services which provide the end user service.

As you create the microservices you have a constantly consider if the code you write is specific to one service or would be better split out into a library.

There are costs associated to creating a library in terms of
- creating a new project
- thinking about the functionalty in a generic reusable way
- adding to CI
- deploying to an artefact repository
- describing the functionality so it can be consumed in the future
- the set up to consume the library

You dont pay this 'libraritization' cost if you leave the functionality within an micro service project.  Of course you may find yourself fixing the same bugs in multiple places if you do end up needing the same logic in multiple places.

When do you make the decision that splitting some functionality out into a library has a benefit that exceeds the cost?
 
## Why open source a library?

Why do you want to open source functionality
- to take advantage of the fantastic services which are available for open source code including CI, source control, security validation
- to simplify how your functionality is consumed by users
- to increase the chance the code will be looked at used and improved by others

The benefit to you and your customer will be a lower cost software delivery than if you either
- dont produce libraries
- try to keep those libraries internal to your software delivery life cycle

In order to open source functionality it is likely there will be objections to overcome including:
- it is our customers ip
- its our know how even if not our IP
- why not just keep it private, its safer

If the code is truly a competitive advantage for your customer you will not want to open source it.   However I would argue that code which fits this criteria is going to be a very small fraction of software written.  If the code is not truly significant and unique to your customer there is a real chance that some one else is contributing the software to open source and you should probably be using/improving that code base rather than rolling your own.

The 'know-how' objection is comes from under appreciation of the difficulty in reuseing software. Just because it is written and deemed a library does not mean it will either be consumed or consumed effectively. In addition to producing a library it needs to be
- discoverable
- understandable
- functioning
- applicable - save the consumer effort they would otherwise have to invest more than what they expect to spend in simple writing their own.


