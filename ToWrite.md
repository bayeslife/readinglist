# Topics that I should write about

## Cheap Quality

Quality is an aspiration for most teams building software.
However attainment of quality can be an expensive goal.  Hiring test staff, designing test cases, executing tests are all time consuming activities.

The goal of quality software is especially difficult to attain when attempting to develop software quickly and for specific project targets.
Code developed for a single purpose is likely to have constraints which make it difficult to use in other contexts from that originally encounted.

This realization identifies what is generally meant when we identify software as quallity.  We generally mean software that is successfully used in a number of different contexts.

How is quality generally attained?   I would think that quality is generally attained only when software is used in multiple contexts and has been through a number of iterations such that unnecessary constraints are removed from the solution.
Quality can be attained when software is developed over iterations and there is some way to ensure that changes retain quality previously engineered into the solution.

Do we need to give up on quality when developing software quickly?

Qualty becomes less and less expensive when components are re-used frequently.   The software is exercised in different contexts and issues are feed back to improve versions to support execution in those additional environments.

How does this realization inform us about developing quality software rapidly?

The hypothesis is that it is important to
- where possible break the work down into components most of which already created and largely which need to be used rather than created
- after creating a solution be sure to break the solution down into components that solve independent problems in a relatively isolated way

## A stencil of icons for stream processing

A set of icons for stream processing

## How separate can Authorization Management be from identity mgt and service delivery?

YOu have a service which you do or maybe dont control.  You want to provide it to authorized users so it has some specific context when they use it.

Users should be able to choose their identity providers...as its their identity.
Service Delivery should be able to choose their Authorization providers...as they want certain service level.

Authorization should be a pillar of management independent of identity mgt and service delivery.
I should be able to 
- have my end users in N different identity provides (Google, Azure AD, Facbook, local db, ...)
- have my app resources at N different end points
Then manage
- user accesses protected resource gets redirected to Authorization server
    - Authorization Server 
        - request user for their identity provider and redirects there with some context
        - Authorization Server then starts process to Authorize person
            - could be request to resource owner
        - When Authorization is granted take the user back to the resource with appropriate access token

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


