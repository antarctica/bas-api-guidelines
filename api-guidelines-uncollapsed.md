# API Guidlines

Version:

* **0.1.0** - November 2014 - Draft

Authors:

* [Felix Fennell](mailto:felnne@bas.ac.uk) (BASIS)

Status: 

* **These guidelines have not yet been adopted**. When they are, they will automatically become version 1.0.0.
* **Adopted versions** of these guidelines will be tracked in the **master** branch of the [API Guidelines repository](), tagged by version.
* **Draft versions** of these guidelines will be tracked in the **develop** branch of the [API Guidelines repository]().

## Conventions & Terms

**MUST** / **MUST NOT** - As defined by [RFC 2119](https://www.ietf.org/rfc/rfc2119.txt).

**SHOULD** / **SHOULD NOT** - As defined by [RFC 2119](https://www.ietf.org/rfc/rfc2119.txt).

* REST(ful) - [Representational state transfer](http://en.wikipedia.org/wiki/Representational_state_transfer)
* Method - [Methods are actions performed on a resource, accessed through an endpoint](http://restful-api-design.readthedocs.org/en/latest/methods.html)
* Resource - [Similar to the concept of an object in programming](http://restful-api-design.readthedocs.org/en/latest/resources.html)
* Request - [A request for something, such as a resource](http://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol#Request_message)
* Response - [A reply to a request, such as a representation of a resource](http://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol#Response_message)
* CRUD - **C**reate, **R**etrieve (**R**ead), **U**pdate, **D**estroy (**D**elete).

Guidelines use a numbered prefix like this:

#### [X.X] Guideline

 e.g. 

####[2.4] Guideline

Important information is shown **like this**.

## Audience

These guidelines are aimed at API authors or those working closely with them, such as a technical managers if an API is used with an project.You do not need to know these guidelines to consume an API based on these guidelines. The documentation for the respective API **SHOULD** contain any information you require.

These guidelines are written for a technical audience and use technical terms where appropriate. The *Conventions & Terms* section will document any terms that may not be generally known by such an audience, or where a term is used to mean something other than its common definition.

## Feedback

**Feedback and discussion is strongly encouraged,** either formally through revisions to this document, or informally by contacting any of the authors.

## Acknowledgements

As noted later, **BAS APIs are not significantly unique**, therefore large parts of guidelines produced by others are directly applicable here. Consequently, large parts of these guidelines are based on other peoples work, particularly those with significant experience.

* [Government Digital Service - Service Manual](https://www.gov.uk/service-manual)
* [18F - 18F API Standards](https://github.com/18f/api-standards)[1]
* [Interagent - HTTP API Design](https://github.com/interagent/http-api-design)[2]

[1] 18F are the US equivalent of the GDS.  
[2] AKA Heroku

## Aims & Objectives

The aims of these guidelines are:

* To ensure APIs created by BASIS follow best practice in a way that makes them better to maintain and use.
* To ensure, where appropriate, APIs created by BASIS are of a consistent design with one another, so as to be able to share experience and ease maintaining multiple APIs.

These aims will be achieved through these objectives:

* Provide a series of guidelines focusing on the *design* and *behaviour* of APIs[1].
* Promote the use of standards, best practice and how these create better APIs.
* Ensure technologies and approaches used to create APIs are justified.
* Provide, real world, non-abstract resources and practices which creators can use to provide functionality that meet these guidelines[2].
* In some cases, make opinionated decisions, with explanations why these have been made.
* Ensure any relevant requirements that apply to BASIS through BAS, NERC, Government, etc. are followed.
* Ensure these guidelines are updated in a timely fashion to ensure guidance remains relevant and APIs remain useful.

[1] These guidelines provide one way of doing things that might not always be the only way nor the best way. In such cases, feel free to move away from the guidelines. However such APIs **MUST** state they do not follow these guidelines. You should also be aware of any potential repercussions such as security issues, consistency issues, etc.  

[2] These are not required implementations, where others are more suitable they should be used.

## Scope

* Currently these guidelines apply to APIs created by members of BAS Information Services only.
* These guidelines apply to both new and existing APIs, which may require some existing APIs to be modified [1].
* These guidelines apply to both internal and external APIs. Internal in this case refers to APIs used solely within BASIS, BAS or NERC.
* These guidelines apply to HTTP based 'RESTful' APIs only. Web and data services in general are out of scope.
* The specific technology stack used within an API is out of scope. These guidelines provide criteria on how choices in technology should be made and how these should be justified, but do not specify what languages, frameworks, methodologies should be used.

[1] APIs where this cannot be achieved are still in scope of these guidelines but can choose not to implement them. Such APIs should state this in their documentation.

## General Principles

### [x.x] APIs **SHOULD** be consistent but not uniform, using the most appropriate solution for each need

Consistency, within these guidelines, refers to not only providing a similar response format, errors, etc. but also the *stability* (amount of change) and *sustainability* (long term maintenance and availability) of the API.

This is the ninth GDS Design Principle and echoed below for convenience.

> "Wherever possible we should use the same language and the same design patterns -- this helps people get familiar with our services. But, when this isn't possible, we should make sure our underlying approach is consistent. So our users will have a reasonable chance of guessing what they're supposed to do.

> This isn't a straitjacket or a rule book. We can't build great services by rote. We can't imagine every scenario and write rules for it. Every circumstance is different and should be addressed on its own terms. What unites things, therefore, should be a consistent approach -- one that users will hopefully come to understand and trust -- even as we move into new digital spaces."

Wherever possible APIs should use consistent terminology and meaning, including field names, actions, etc. Wherever possible these should be commonly used terms used elsewhere.

APIs will not all serve the same purpose, however there are a number of common types that should, where appropriate, be consistent with one another. Some examples are listed in the 18F API Standards and echoed here for convenience:

> *  "*Bulk data*. Clients often wish to establish their own copy of the API's dataset in its entirety. For example, someone might like to build their own search engine on top of the dataset, using different parameters and technology than the "official" API allows. If the API can't easily act as a bulk data provider, provide a separate mechanism for acquiring the backing dataset in bulk.

> *  *Staying up to date*. Especially for large datasets, clients may want to keep their dataset up to date without downloading the data set after every change. If this is a use case for the API, prioritise it in the design.

> *  *Driving expensive actions*. What would happen if a client wanted to automatically send text messages to thousands of people or light up the side of a skyscraper every time a new record appears? Consider whether the API's records will always be in a reliable unchanging order, and whether they tend to appear in clumps or in a steady stream. Generally speaking, consider the "entropy" an API client would experience."

Sources:

* [Ninth Principle - GDS Design Principles](https://www.gov.uk/design-principles#ninth)
* [APIs - Names Reinforce Conventions - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#names-reinforce-conventions)
* [Naming Principles - Microformats](http://microformats.org/wiki/naming-principles)
* [18F API Standards - Design For Common Use Cases - I8F](https://github.com/18f/api-standards#design-for-common-use-cases)

### [x.x] APIs **SHOULD** be as simple as possible

Simple APIs, and code, are easier to understand than complex APIs and code. This increases the maintainability of the API, and through having 'less moving parts' creates fewer places for bugs to hide.

Simple APIs are quicker to iterate on, document and release than more complex APIs. For users, it is easier and quicker to use a simple API, especially when revisiting implementations created in the past.

APIs **SHOULD NOT** do more than they need to. If another service already provides a service we **SHOULD** use or recommend this, we **SHOULD NOT** duplicate it ourselves.

For example, an API for providing the locations of BAS ships could include a current weather report from a third party. Since this weather information can be requested directly (rather than bundled by us) it **SHOULD NOT** be included in our API. Instead information on where to get this weather data from, and preferably an example, **SHOULD** be documented.

Doing this keeps our API as simple as possible and lets us focus on making what we need to provide as useful as possible. We should let others concentrate on solving other needs.

This is essentially the UNIX philosophy i.e. 'do one thing and do it well', and the second GDS Design Principle.

Sources:

* [UNIX philosophy - Wikipedia](http://en.wikipedia.org/wiki/Unix_philosophy)
* [Keep It Simple Stupid (KISS) Principle - Wikipedia](http://en.wikipedia.org/wiki/KISS_principle)
* [Second Principle - GDS Design Principles](https://www.gov.uk/design-principles#second)
* [APIs - Consuming and Using APIs - GDS Design Principles](https://www.gov.uk/service-manual/making-software/apis.html#consuming-and-using-apis)

### [x.x] APIs **SHOULD** be clear and explicit in their operation, returning helpful errors 


APIs **SHOULD NOT** try to 'guess' or make assumptions about what what the user wants. If a request doesn't make sense the API **SHOULD** say so by returning an error.  

*Guessing* introduces unnecessary logic within the API, making it more complex, increasing the changes of something going wrong. This decreases reliability and increases unpredictability. However, APIs **SHOULD** be *helpful*.

For example, an API method takes a start date as a filter for some dataset, the method expects a date in the form `YYYY-MM-DD`. A request is made using a date `2004/10/14`.

This request **SHOULD** fail, stating the start date given is not recognised as valid.

It is clear the date is valid, but is in the wrong format. Whilst it is possible (and likely trivial) to detect this and convert the date into the right format the API **SHOULD NOT** do so.

In most cases, it would be necessary to add code to check for this, if the code is refactored and this is missed this request will now fail when previously it succeeded. This will likely have an impact on any service using the API and cause confusion (i.e. not clear and unambiguous) and require debugging. Further refactoring, probably caused by a submitted bug report, will then be needed to fix the error.

In this case, the delimiter, `/` used is common and would typically be included in any *guessing* code. However if a `;` was used instead, and not coded for, that request would fail. This would mean the two requests, which contain the same fault, would be treated differently.

Instead, a simple `if date == format` should be used, if it fails, for any reason, an error **SHOULD** be returned. The error **SHOULD** explain:
 
* Why the request failed, possibly with links to documentation (the date wasn't valid)
* The syntax that was expected (`YYYY-MM-DD`, e.g. `2004-07-23`)
* The value used in the request ('2004/10/14')

This shows, clearly and unambiguously, why the request failed and how to correct the mistake. Importantly, regardless of the input used, this method will, from first use, only succeed where the date is correctly formatted.

In addition, an appropriate status code should be used to indicate more generally the type of error that has occurred. Errors caused by us, or the API should use a status code in the `5XX` range. User errors should use a status code in the `4XX` range.

Sources:

* [APIs Explicitly Set Expectations - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#explicitly-set-expectations)
* [18F API Standards - Error Handling - I8F](https://github.com/18f/api-standards#error-handling)

### [x.x] APIs **SHOULD** make things as easy as possible, whilst remaining clear and consistent

If there is something we can do to make things easier for the end user we should do so, providing this is clearly explained, either in the response or in documentation.

This is Principle 4 of the GDS Design Principles, echoed here for convenience.

> "Making something look simple is easy; making something simple to use is much harder -- especially when the underlying systems are complex -- but that's what we should be doing.

> With great power comes great responsibility -- very often people have no choice but to use our services. If we don't work hard to make them simple and usable we're abusing that power, and wasting people's time."

Sources:

* [Fourth Principle - GDS Design Principles](https://www.gov.uk/design-principles#fourth)

### [x.x] APIs **SHOULD** be as resilient as possible

Where we create APIs that rely on third parties we must ensure we have plans in place for where these services are either temporally or permanently unavailable in the future.

When evaluating whether to use an external service factors such as the reputation of the service, the cost (and if this likely to change), availability (can the service scale to the same degree we can) and support all need to considered. This applies both to external services provided internally (i.e. by ourselves, BAS, NERC) or by third parties.

These factors need to weighed against the importance of the functionality such services provide. For services providing core functionality, a more defensive, conservative approach should be followed.

It is unfeasible to provide all services ourselves, credit card processing for example **SHOULD** be left to a payment gateway, however we should create APIs in such a way that reliance on a particular service is abstracted. This ensures we can swap out services, potentially for newer, better ones, without having to change core 'business' logic. 

Sources:

* [APIs - Service Agreements and Resilience - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#service-agreements-and-resilience)

### [x.x] Where appropriate, APIs **SHOULD** use best practice for solving common problems

APIs **SHOULD NOT** 'reinvent the wheel'. The types of APIs BAS will commonly create will not be unique. They therefore don't require unique functionality or solutions to common problems.

Using a common solution can utilise prior or community knowledge, reducing implementation and support costs. Existing tooling, frameworks and can be easily applied, increasing interpretability and looser coupling between different solutions.

For example, content negotiation for determining response format is a solved problem. Rolling our solution would take time, not cover all edge cases and would require all support to be provided by us. Using the *standard* solution means we benefit from the experience of others and more people are able to provide support (e.g. StackOverflow etc.).

A distinction should be made between *best* practice, which should be followed, and *common* practice, which whilst widespread is not "a good idea". Examples of *common* practice which are justifiable to avoid include:

* Solutions which break or mis-use standards.
* Solutions which not sufficiently secure, in situations where a more secure alternative exists, or for sensitive information, where any solution exists.
* Solutions which are 'hacks' or 'lazy' approaches, where a 'proper' approach is available, or rely on 'quirks' or 'side effects' to achieve their purpose.

These approaches, especially the latter 'quirk' kind, are typically not sustainable as their behaviour could change at any time, often without warning. The results of this could, at best, break the approach used, or at worst, change the result of the approach. This could potentially suddenly introduce new security flaws or inadvertently exposing information presumed to be safe.

A good example of a *common* solution is [JSONP](http://en.wikipedia.org/wiki/JSONP) which is essentially a hack so as not to use the *best* solution, [CORS](http://en.wikipedia.org/wiki/Cross-origin_resource_sharing).

Sources:

* [HTTP API Design - Generate Structured Errors - Interagent](https://github.com/interagent/http-api-design#generate-structured-errors)

### [x.x] Where appropriate, APIs **SHOULD** be open, and made available publicly

Given BAS is Government organisation (according to Wikipedia so it must be true) our work should visible and accessible. Providing APIs aids this by offering data in an organised, logic way in convenient formats, ideally without involvement with BAS staff.

In addition to API outputs, the research, design and code of APIs themselves can prove useful to others and ourselves. We benefit enormously from the work of others, through open sourced ideas and technologies, it is therefore right we make whatever we can available for others.

In general the more people that use our APIs, and able to see how they work, the higher the chance of feedback. Either bugs/inaccuracies in our code or data we can correct, or 'have you thought about this' type ideas.

In addition APIs and their code being publicly available, where feasible associated issue trackers, wiki's and other sources of information **SHOULD** be made available. This gives users an increased understanding of the current status of an API, its history, challenges and how these were resolved etc. This helps users evaluate our APIs with more confidence and prevents repeating old discussions.

This is the tenth GDS Design Principle.

Sources:

* [Tenth Principle - GDS Design Principles](https://www.gov.uk/design-principles#tenth)
* [APIs - Be Public By Default - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#be-public-by-default)
* [18F API Standards - Point of Contact - I8F](https://github.com/18f/api-standards#point-of-contact)

### [x.x] Where appropriate, APIs **SHOULD** use established standards and open formats

Good standards encourage interoperability through consistency between different systems implementing the same standards.

Different standards target different *layers*, technologies or approaches used within an API. Conformance to appropriate standard, at whatever level, can be used to justify technology choices for example. In such cases it usually isn't necessary to verify a technology meets a standard but technologies that do (or claim to) **SHOULD** be preferred over those that don't.

Following standards, or using standards compliment technologies, typically bring benefits such as community/hive knowledge (e.g. StackOverflow etc.) and compatibility with tooling, saving time and generally giving a better experience than non-standard alternatives.

The [HTTP Protocol](https://tools.ietf.org/html/rfc2616) is a good example of a standard, using it means we can use a variety of tools (web browser, caching layers, load balancers etc.) and frameworks provided by others with a high confidence these will understand each other. End users will also typically understand, if not expect, the use of this standard. 

Another, technology specific, good example, is the [PSR-4 Autoloader](http://www.php-fig.org/psr/psr-4/) standard for automatically loading PHP classes. Using this standard reduces the effort to use unfamiliar technologies, encouraging experimentation and making rapid iteration more achievable. Similarly a common standard encourages the creation of associated tooling, such as package managers and IDE/editor support.

Data formats **SHOULD** be chosen based on there suitability to the data being represented and interpretability.

Data formats are discussed later in this document, however in general, data formats should be as open as possible. Similar to technologies, proprietary data formats can become obsolete or expensive to maintain limiting their long term availability.

Sources:

* [APIs - Just Use the Web - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#just-use-the-web)
* [APIs - Choosing Appropriate Formats - GDS Service Manual](https://www.gov.uk/service-manual/user-centred-design/choosing-appropriate-formats.html)

### [x.x] Where appropriate, APIs **SHOULD** favour proven and open source alternatives over experimental or proprietary, alternatives

A experimental or immature technology may be discontinued. If resources are not available to reimplement the features that technology provided, the API may be degraded or cease to function. Similarly, if proprietary technology is used and is no longer supported or open sourced, it will become obsolete and incompatible with newer technologies.

Ongoing, variable licensing costs may force the removal of a proprietary technology. If resources are not available to reimplement the features that technology provided, the API may be degraded or cease to function.

Each time a technology is changed it may introduce new dependencies and constraints, such as needing to remove a feature that the new technology cannot provide itself. New bugs may be introduced, potentially across the API. Such changes introduce change, which impact on the consistency of the API.

Sources:

* [Choosing Technology - GDS Service Manual](https://www.gov.uk/service-manual/making-software/choosing-technology)
* [Technology Code of Practice - GDS Service Manual](https://www.gov.uk/service-manual/technology/code-of-practice.html)

## Need Driven

### [x.x] APIs **MUST**  meet the needs of their users

Ideally all stakeholders should be involved in the development of an API, including data providers, API creators, relevant project mangers, significant end users and representative users.

For simple APIs, this may not be many people and simple to organise. Others may require more extensive research and engagement with users, including resolving conflicts through negotiation.

Testing is important to ensure APIs we create meet these needs, and logging and monitoring should be used to track this over time. Feedback and retrospectives should be used to ensure that we don't repeat mistakes in the future, and support and emphasise things that worked well. 

This is the first of the GDS Design Principles.

Sources:

* [First Principle - GDS Design Principles](https://www.gov.uk/design-principles#first)
* [APIs - Testing - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#testing)

### [x.x] APIs **MUST** allow user feedback, and this **MUST** be taken seriously

Ideally the individual responsible for each API **SHOULD** be contactable directly.

Feedback **MUST** be treated seriously, particularly in regards to usability problems.  

Examples of this type of feedback might include:

* A user has made a reasonable attempt to achieve a task the API claims to support using provided documentation/examples and limited experimentation.
* A user reports that something doesn't work as expected or is unclear how something should be used.
 
Sources:

* [18F API Standards - Point of Contact - I8F](https://github.com/18f/api-standards#point-of-contact)

### [x.x] APIs **SHOULD NOT** be created in isolation, and we **SHOULD** use our own APIs 

API creators SHOULD be also be API consumers, this is the quickest and easiest way to validate our APIs do what it should.

API creators SHOULD also take part in any discussions on the needs of an API. This reinforces *why* the API is needed and helps ensures these needs are met.

Wherever possible, APIs should be implemented in a real system, usually online. Again this highlights any problems in using an API and ensuring APIs are practical, if not *nice* to use.

Sources:

* [APIs - Build an API By Building With the API](https://www.gov.uk/service-manual/making-software/apis.html#build-an-api-by-building-with-the-api)
* [18F API Standards - Using One's Own API - I8F](https://github.com/18f/api-standards#using-ones-own-api)

## API Development

### [x.x] APIs **SHOULD** have a single owner responsible for its delivery and support

This person **SHOULD**:

* be reasonable for making sure the API follows these guidelines
* be involved in the day to day creation and running of the API, they **SHOULD NOT** be a symbolic figurehead
* be responsible for the allocation of available resources to that API
* be contactable by users of the API, and **SHOULD** personally review and act on any feedback provided

Sources:

* [18F API Standards - Point of Contact - I8F](https://github.com/18f/api-standards#point-of-contact)

### [x.x] APIs **SHOULD** be loosely coupled

This means the use of interfaces to separate tasks with specific implementations, and repositories to separate data sources from how and where that data is accessed.

This ensures the APIs we create a modular and adaptable to change. This applies at a service level (changing payment processor or even database backend) and at a local code level by designing properly scoped functions and clear separation of concerns.

Sources:

* [APIs - Code Integration - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#code-integration)
* [Seperation of Concerns - WikiPedia](http://en.wikipedia.org/wiki/Separation_of_concerns)

### [x.x] APIs **SHOULD** use source control

Git is preferred, specially the NERC Stash repository provided by CEH.

APIs **SHOULD** adopt a suitable branching model for separating development and production codebases, and for using tools such as continuous integration and task such as code reviews.

By convention a *develop* branch should reflect the version of the API under active development, and a *master* branch reflecting the latest stable version.

Wherever possible, API source code **SHOULD** be made available publicly. This increases the number of people who can review our code for bugs and mistakes and maybe offer suggestions on how to do things better. It also forces us to write better code, by avoiding 'hacks' using proper structuring and ensuring code is readable and well explained.

Sources:

* [Why Should I use Source Control - Stack Overflow](http://stackoverflow.com/questions/1408450/why-should-i-use-version-control)

Resources:

* [Stash - CEH](https://stash.ceh.ac.uk)
* [Comparing Workflows - Atlassian Tutorials](https://www.atlassian.com/git/tutorials/comparing-workflows)

### [x.x] APIs **SHOULD** use issue tracking

These guidelines have no preference on the wide range of issue trackers that are available. The type of issue tracker you choose will depend on the audience of the API, the number and range of people contributing to the API and the complexity of the issues that will need to handled.

For small projects released to the public tools like the GitHub or BitBucket issue trackers offer good accessibility for users and contributors and are free to use. However they lack more complex features such as assignments, custom issue states and associations.

For larger projects or those focused on an internal or NERC audience, it is recommended you use Jira, of which NERC has an instance provided by CEH. An added benefit of using this system is integration with other services such as Stash.

As with source code, wherever possible the issue tracker should be a publicly available resource. This allows users to check for previously reported issues and encourages greater debate, and ideally better APIs through openness.

Sources:

* [Why Use Bug Tracking Software - Stack Overflow](http://stackoverflow.com/questions/765968/why-use-bug-tracking-software)

Resources:

* [Comparison of Issue Tracking Software - Wikipedia](http://en.wikipedia.org/wiki/Comparison_of_issue-tracking_systems)
* [Github Issues 2.0 - Github Blog](https://github.com/blog/831-issues-2-0-the-next-generation)
* [Jira - CEH](https://jira.ceh.ac.uk)
* [Stash - CEH](https://stash.ceh.ac.uk)

### [x.x] APIs **SHOULD** be robustly tested

This takes a number of forms:

* Automated testing using linters, test suites & continuous integration, mocked services etc.
* Human testing through passive and active feedback during alpha/beta/live stages of development

Sources:

* [APIs - Testing - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#testing)

## API Design

### [x.x] APIs **SHOULD** use `UTF-8` for character encoding 

The 18F API Standards summarise the benefits of using this, they are echoed here for convenience:

> "Expect accented characters or 'smart quotes' in API output, even if they're not expected.
> An API should tell clients to expect UTF-8 by including a charset notation in the Content-Type header for responses.
> An API that returns JSON should use: `Content-Type: application/json; charset=utf-8`"

Sources:

* [18F API Standards - Just Use UTF-8 - 18F](https://github.com/18f/api-standards#use-utf-8)

Resources:

* [UTF-8 Everywhere](http://utf8everywhere.org/)

### [x.x] APIs **SHOULD** use `ISO 8601` and `UTC` for dates and times

The 18F API Standards summarise the benefits of using this, they are echoed here for convenience:

> "For just dates, that looks like 2013-02-27. For full times, that's of the form 2013-02-27T10:00:00Z.
> This date format is used all over the web, and puts each field in consistent order -- from least granular to most granular."

Sources:

* [18F API Standards - Use A Consistent Date Format - I8F](https://github.com/18f/api-standards#use-a-consistent-date-format)
* [HTTP API Design - Use UTC Times Formatted in ISO8601 - Interagent](https://github.com/interagent/http-api-design#use-utc-times-formatted-in-iso8601)

### [x.x] APIs **SHOULD** use unique ids for resources

Each resource **SHOULD** be identified by a unique identifier, ideally a UUID ***SHOULD** be used. This ID **SHOULD** be unique all instances of an API and ideally other APIs as well.

If using UUIDs, version 4 or 5 is recommended and should be represented in lower case.

Sources:

* [HTTP API Design - Provide Resource (UU)IDs - Interagent](https://github.com/interagent/http-api-design#provide-resource-uuids)

### [x.x] Where Appropriate, resources **SHOULD** use `created_at` and `modified_at` timestamps

The created at timestamp should be set when the object is first created and **SHOULD NOT** change. The modified at timestamp **SHOULD** change whenever a resource is modified.

There may be resources where using these attributes don't make sense, in such cases they **SHOULD NOT** be used, as this may create confusion.

Sources:

* [HTTP API Design - Provide Standard Timestamps - Interagent](https://github.com/interagent/http-api-design#provide-standard-timestamps)

## Documentation

### [x.x] APIs **MUST**  provide end user documentation

It isn't feasible to cover exactly how each API should be documented as this will depend on its purpose, intended audience and other factors. However in general APIs **MUST** be well documented so it is clear to users what the API can do and how they should use it to achieve what they want.

However there it is possible to identify some key requirements for API documentation. It **MUST** be clear, concise and well organised. It **MUST** care to two key audiences, users, looking to evaluate the API, and existing users, looking for specific information.

How you decide to write and structure your documentation is up to you. To ensure that common elements are not forgotten a list of suggested sections/topics is given here. You do not have follow all of these items, and you **SHOULD NOT** include any that do not fit your API, this will confuse people.

It is suggested to divide documentation into two parts:

* Overview information
* Endpoint information

Overview information **SHOULD** cover:

* Security and authentication, including acquiring and using authentication tokens, if used.
* API stability, versioning and deprecation policy, including how to select the desired API version.
* Common request and response headers.
* Error serialisation format.
* Rate limiting
* Data sources, accuracy and limitations 
* Feedback, Issues, contacts
* Mailing list - i.e. some way to stay up to date with any changes.
* Contribution policy
* Real world examples

Endpoint information **HSOULD** cover, for each endpoint:

* Access (including endpoint URL, anonymous/authenticated status, required authorisation)
* Stability & Deprecation
* Request parameters & headers
* Response headers, supported data types output
* Associated resources
* Additional information as required

Sources:

* [APIs - Explicitly Set Expectations - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#explicitly-set-expectations)
* [APIs - Practice Service Evolution - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#practice-service-evolution)
* [Security - Atlassian REST API Design Guidelines (V1)](https://developer.atlassian.com/display/DOCS/Atlassian+REST+API+Design+Guidelines+version+1#AtlassianRESTAPIDesignGuidelinesversion1-Security)
* [18F API Standards - Notifications of Updates - I8F](https://github.com/18f/api-standards#notifications-of-updates)
* [HTTP API Design - Provide Human Readable Docs - Interagent](https://github.com/interagent/http-api-design#provide-human-readable-docs)
* [HTTP API Design - Describe Stability - Interagent](https://github.com/interagent/http-api-design#describe-stability)

Resources:

* Good Examples
	* [Stripe](https://stripe.com/docs/api)
	* [New York Times](http://developer.nytimes.com/docs/read/article_search_api_v2)
	* [Twilio](https://www.twilio.com/docs/api)

### [x.x] APIs **SHOULD** provide real world examples

In addition to through and accurate documentation, examples of how to make requests for different scenarios and responses which would be returned **SHOULD** be provided.

This aids users in evaluating if the API will provide the information they are looking for, more so than verbose descriptions of responses.

When implementing an API end users can use examples to get started quickly. Therefore examples **SHOULD** be functional (i.e. use a real ids) using safe, sensible defaults for real world, typical requests.

Documentation **SHOULD** clarify any extreme values or lists of acceptable values, these **SHOULD NOT** be defined within examples.

Examples **SHOULD** be runnable with a minimum of effort, ideally from the browser or the command line. Provision for features such as authentication/authorisation should be made, such as:

* Use public methods (where available)
* Use test credentials which may return fake data but sufficiently similar to read data to be useful for testing, e.g. give fake but realistic ship positions.
* Show typical responses users can inspect to get a good idea what they would get.

Complex APIs, where requests cannot be tested within a browser, **SHOULD** still offer some way to experiment. Commonly this is done using an API 'explorer' or 'playground'. In addition to self hosted solutions there are a number of SAAS options, though millage may vary in supporting complex APIs.

Sources:

* [APIs Document by discovery... and Example - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#document-by-discovery-and-example)
* [HTTP API Design - Provide Executable Examples - Interagent](https://github.com/interagent/http-api-design#provide-executable-examples)

Resources:

* Examples/Generators:
	* Self hosted:
		* [Swagger](https://helloreverb.com/developers/swagger)
		* [Slate](https://github.com/tripit/slate)
	* SASS:
		* [Apiary](http://apiary.io/blueprint)
		* [Mashape](https://www.mashape.com/)
	* Bespoke/Custom: 
		* [Facebook API Tools](https://developers.facebook.com/tools/)
		* [Guardian API Explorer](http://open-platform.theguardian.com/explore/)
		* [Google Search for API Explorer](https://www.google.co.uk/search?hl=en&q=API+explorer)

### [x.x] APIs **SHOULD** provide developer documentation

Developer documentation **SHOULD** contain:

* A description of the technology stack used by an API and how this should be provisioned to allow new instances of the API to be created, either for further development or deployment.
* In addition, a 'getting started' walkthrough of how to checkout the API source code through to launching the API into production. This is crucial for new developers, especially where you are using non-standard or custom technologies.
* A brief overview of the development process, issues that were encountered, any non-straight forward decisions that were taken and why, etc. This aids new developers understand how the API was built and why it works the way it does. This is especially important if non-standard design decisions were made.

The standard of documentation for both internal and externally released APIs **SHOULD** be the same, i.e. you should assume the developer has never used one of our APIs before. It is reasonable to assume knowledge of basic programming terminology and concepts and a certain familiarity with the BAS domain.

Where useful and available, link to meeting minutes, process reports or other sources of information that may have been created as part of a development. This can provide more context without much effort on your part.

### [x.x] APIs **SHOULD** be backed by a schema

This ensures all elements of an API are defined in a structured, testable, way and can be validated either by hand or using automatic tools.

Sources:

* [HTTP API Design - Provide Machine Readable JSON Schema - Interagent](https://github.com/interagent/http-api-design#provide-machine-readable-json-schema)

Resources:

* [Understanding JSON Schema - Michael Droettboom, Space Telescope Science Institute](http://spacetelescope.github.io/understanding-json-schema/)

## Versioning

### [x.x] APIs **MUST** use versioning using whole integers

New API versions **SHOULD** replace older versions, therefore older versions **SHOULD** be deprecated.

### [x.x] API versions **SHOULD** map to major releases

API versions are not alternatives, they are linear progressions, ideally improving over time.

###[x.x] The API version **MUST** be the first token in a URL path, prefixed by a "v"

For example `api.nerc-bas.ac.uk/V2/ships`.

Sources:

* [Version Control For APIs - Atlassian REST API Design Guidelines (V1)](https://developer.atlassian.com/display/DOCS/Atlassian+REST+API+Design+Guidelines+version+1#AtlassianRESTAPIDesignGuidelinesversion1-VersionControlforAPIs)

### [x.x] APIs **MUST NOT** assume a version for requests that do not specify one

APIs **MUST NOT** use conventions such as `/latest/`, `/current/`, `/head/` etc. as pointers to the latest API version. This behaviour is not clear or unambiguous, requests made in this way may suddenly fail if a breaking change is introduced to a new version.

Instead users **MUST** explicitly state the version they wish to use. If no version is provided, the API **MUST** return a fatal error until one is provided.

### [x.x] APIs **MUST** preserve backwards compatibility within a version

APIs **MUST NOT** introduce braking changes *within* an API version. If you need to do this create a new version.

Examples of changes that can be implemented in the current version:

* New resources (with associated methods)
* New methods for existing resources
* New data formats
* New attributes or elements on existing data types

Examples of changes that **MUST** be implemented in a new version:

* Removed or renamed methods/resources/URLs, including changes to HTTP verb
* Changes to the data returned by a method

Sources:

* [APIs - Practice Service Evolution - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#practice-service-evolution)
* [Version Control For APIs - Atlassian REST API Design Guidelines (V1)](https://developer.atlassian.com/display/DOCS/Atlassian+REST+API+Design+Guidelines+version+1#AtlassianRESTAPIDesignGuidelinesversion1-VersionControlforAPIs)
* [18F API Standards - I8F](https://github.com/18f/api-standards)

### [x.x] APIs **SHOULD** try to be compatible with older versions, providing they remain clear and unambiguous

For example, an API method is moved from `/ships` to `/fleet/ships` to be better organised, no other aspects of the method are changed.

This represents a breaking change, as requests made to `/ships` will no longer return what they did previously. In this case a request made to the earlier `/ships` and newer `/fleet/ships` will be identical (other than the URL obviously). Backwards compatibility can therefore be preserved by using a `301 Moved Permanently` header to redirect requests made to the old method to the new.

This remains clear and unambiguous by informing the user, 'this has moved to here', the user can then update their requests accordingly in their own time, which is nice.

Sources:

* [APIs - Practice Service Evolution - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#practice-service-evolution)

### [x.x] Where appropriate,  APIs **SHOULD** support old versions

It is not reasonable to assume all users will upgrade to newer API versions at the same time. Therefore old APIs **SHOULD** continue to be supported, for a limited period, to allow users to upgrade in their own time.

The length of this time period will depend on the audience of the API, for internal APIs the period can be quite short, for external APIs a longer period should be given. The number of users of the API should also be taken into account, which should be judged from API analytics and logs.

Wherever possible users **SHOULD** be notified of new API versions in advance, increasing the likelihood of a quicker adoption by allowing testing. Additionally, requests made to deprecated API versions **SHOULD** inform the user the version is deprecated and how they can use the new version.

APIs **SHOULD** clearly state their deprecation policy within their documentation, this allows users to evaluate if they can commit to this schedule before a version change occurs.

The number of API versions that should be supported will depend on the same factors as above and the rate at which new versions are released. Ultimately these are judgement calls with internal resources for supporting these older version being the limiting factor.

Supported, in these guidelines, mean older versions should remain accessible, bugs and faults should be addressed (as these will likely exist in newer versions as well). Security issues **MUST** be addressed, if this is not possible the older version MUST no longer be made available.

Improvements and new features, regardless of whether they maintain compatibility within a version, **SHOULD NOT** be supported in older versions.

Sources:

* [APIs - Practice Service Evolution - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#practice-service-evolution)

### [x.x] **SHOULD** APIs **SHOULD** be forwards compatible, providing they remain clear and unambiguous

APIs should be designed to be robust and forward thinking, given the speed of evolution on the web.

For example, if a new header is added to later API versions older API versions should ignore it, rather than fail. Documentation should emphasise where different versions may give different responses for the same request, however these situations should be avoided where possible.

Sources: 

* [APIs - Practice Service Evolution - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#practice-service-evolution)

## Security

### [x.x] APIs **MUST NOT** rely on 'security through obscurity'

It is a dangerous fallacy and **MUST NOT** be relied upon.

Sources:

* [Security Through Obscurity - Wikipedia](http://en.wikipedia.org/wiki/Security_through_obscurity)
* [Why is Security Through Obscurity a Bad Idea - Stack Overflow](http://stackoverflow.com/questions/533965/why-is-security-through-obscurity-a-bad-idea)

### [x.x] APIs **MUST NOT** use non-standard cryptography

Simply put Cryptography is hard and we **SHOULD NOT** design it ourselves. Cryptography, encryption, etc. are all excellent examples of when it's better to use something by someone else, or more specifically by someone that knows what they're doing.

Even *implementing* cryptography is different, as a quick internet search will prove. Banks struggle with stuff so it would insane for us to attempt to 'roll our own' cryptography or implementation.

If you think you do need to **STOP!** Consult widely with others (both internally and online) to test your reasoning and ensure you haven't missed something.

Sources:

* [Why shouldn't we roll our own? - Information Security - Stack Exchange](http://security.stackexchange.com/questions/18197/why-shouldnt-we-roll-our-own)
* [Even if You Don't Invent Your Own Cryptography its Still Hard - Neohapsis Labs](http://labs.neohapsis.com/2010/01/19/even-if-you-dont-invent-your-own-crypto-its-still-hard/)

Resources:

* [OWASP](https://www.owasp.org/index.php/Main_Page)

### [x.x] Where appropriate, APIs **SHOULD** allow anonymous access

This means access should require authentication or authorisation, unless it is necessary.

This ensures APIs are easier to experiment with and integrate, especially for semolina like a scientist who just wants to get the information they want as quickly and easily as possible.

Anonymous responses can be externally cached much more easily and effectively, for popular APIs this saves resources and speeds up response times.

Clearly there will be many cases where anonymous access simply isn't tenable (or useful). As a general rule `GET` methods for most resources can be made accessible anonymously, other methods would typically require authentication/authorisation.

In some cases authentication is a useful feature for the end user, such as 'favourites' or usage histories. These are perfectly acceptable and **SHOULD** be offered if they help the user.

Sources:

* [APIs - Be Public By Default - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#be-public-by-default)
* [18F API Standards - API keys - I8F](https://github.com/18f/api-standards#api-keys)

### [x.x] Where appropriate, APIs **MUST** restrict access to sensitive information

This includes anything information that is personally identifying, confidential or privileged (including anything rated as 'OFFICIAL' under the Government Security Classifications.

Authorisation levels should be created according to need, using the principle of least privileged access.

Sources:

* [APIs - Be Public By Default - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#be-public-by-default)
* [Government Security Classifications - GOV.UK](https://www.gov.uk/government/publications/government-security-classifications)
* [Principle of Least Privileged Access](http://en.wikipedia.org/wiki/Principle_of_least_privilege)

### [x.x] Where appropriate, APIs **SHOULD** use common authentication sources

Many APIs will be accessible to the same group of people (i.e. BAS/NERC staff). It would therefore make sense to centralise the verification of user credentials to a central service, or order to keep our APIs as simple as possible, and to reduce the number of passwords users have to remember. 

For internal APIs this central service **SHOULD** be all or part of the NERC Active Directory. This allows the authentication of users to be delegated out completely, saving considerable time and effort. Integration with Active Directory directly or through LDAP is widely supported by a range of technologies and, if correctly implemented, is secure.

It is reasonable to assume users will be able to readily provide their NERC AD account details, and if not we can again delegate password resets to IT Help Desks. This ensures where authentication is needed, it is as painless as possible.

For external (to NERC) users, a similar approach should be adopted where a common authentication source is created to contain these users, to which our APIs authenticate credentials. This may take the form of a formal internal LDAP service or users database or, for academic users, Shibboleth, or for the general public, OAuth for providers such as Google, Facebook and Twitter.

These external authentication sources offer similar benefits as internal sources, they also offer much larger audience sizes and, in some cases, access to additional user information, subject to the user's approval.

The key point to this guideline is APIs **SHOULD NOT** maintain their directory of users for the purposes of authentication.

However, there will likely be times where APIs may need to store information about a user that is specific to that API. In this cases, APIs **SHOULD** store this extra information within the API so as not to 'pollute' the authentication service.

Sources:

* [APIs - Be Public By Default - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#be-public-by-default)

Resources:

* [The UK Access Management Federation](http://www.ukfederation.org.uk/)
* [OAuth](http://oauth.net/)
* HTTP Basic authentication

### [x.x] APIs **SHOULD** use HTTPS

The 18F API Standards summarise the benefits of using HTTPS, they are echoed here for convenience:

> "Any new API should use and require HTTPS encryption (using TLS/SSL). HTTPS provides:

> * *Security*. The contents of the request are encrypted across the Internet.
> * *Authenticity*. A stronger guarantee that a client is communicating with the real API.
> * *Privacy*. Enhanced privacy for apps and users using the API. HTTP headers and query string parameters (among other things) will be encrypted.
> * *Compatibility*. Broader client-side compatibility. For CORS requests to the API to work on HTTPS websites -- to not be blocked as mixed content -- those requests must be over HTTPS.

> HTTPS **SHOULD** be configured using modern best practices, including ciphers that support forward secrecy, and HTTP Strict Transport Security."

For internal testing, the Web & Applications team maintain a internal Certification Authority which can issue certificates on a per domain basis. This simplifies trusting self signed certificates by owning needing to trust the CA certificate. These certificates **MUST NOT** be used externally or for services hosted outside of BAS.

Please contact the [BAS Web & Applications Team](mailto:basweb@bas.ac.uk) for how to request an internal certificate or how to trust the internal CA.

For hosting outside of BAS or non-testing purposes BAS IT maintain certificates for `antarctica.ac.uk` and `nerc-bas.ac.uk`. These are wildcard certificates issued by a well supported Certification Authority.

Please contact the [BAS IT Help Desk](mailto:helpdesk@bas.ac.uk) for how to use these certificates for your API.

Sources:

* [18F API Standards - Always Use HTTPS - I8F](https://github.com/18f/api-standards#always-use-https)

Resources:

* [SSL Labs](https://ssllabs.com/ssltest/analyze.html)

### [x.x] Where appropriate, APIs **MUST** use HTTPS for sensitive information

This includes anything information that is personally identifying, confidential or privileged (including anything rated as 'OFFICIAL' under the Government Security Classifications.

Sources:

* [APIs - Be Public By Default - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#be-public-by-default)
* [Government Security Classifications - GOV.UK](https://www.gov.uk/government/publications/government-security-classifications)

###  [x.x] Where HTTPS is used, APIs  **SHOULD** reject HTTP requests

It is clearer and simpler to support only one protocol and ensures all requests are made securely.

Ideally insecure requests **SHOULD NOT** be accepted, either by refusing the connection or using a `403 Forbidden` response.

Insecure requests **SHOULD NOT** be silently 'upgraded' or redirected to secure alternatives. This introduces ambiguity and requires additional complexity to support. Taking a hard line approach is not as permissive as redirecting but it ensures 'lazy' behaviours are not tolerated.

Sources:

* [HTTP API Design - Require TLS - Interagent](https://github.com/interagent/http-api-design#require-tls)

## Logging & analytics

### [x.x] APIs **SHOULD** collect information about itself to determine user needs and identify problems

Aggregating and analysing request data **SHOULD** inform the future development of our APIs.

Information on which methods and features are used most provides an evidence base for planning future development with the needs of users in mind. This data is unlikely to explain what *new* functionality might be required, but is invaluable in identifying features that are not used.

At a technical level this data is useful at both a macro and micro level. For example, frequent errors can be highlighted to ensure common problems can be identified or fixed swiftly. Or an issue with a specific resource or even request can be flagged for manual review later. Whilst testing may identify some of these types of issue in advance, its not feasible to test every condition and request premonition possible.

By recording factors such as the time taken to generate requests and logging queries/requests to other data sources or services the performance of the API can be measured objectively. Knowing which types of requests result in slow database queries for example can only feasibly be gathered using this type of analysis.

Key to the success of this staggery lies not only in the raw data being available, but in the tools used to process, analyse and present it in a useful fashion. Fortunately a multitude of third party and self hosted solutions are available to assist with this. Given the availability of these tools, and high value for effort ratio of the insight they can be provide, our APIs **SHOULD** use such an approach.

Sources:

* [APIs Document by discovery... and Example - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#document-by-discovery-and-example)
* [APIs - Testing - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#testing)

### [x.x] APIs **SHOULD** log requests using an unique identifier

Each request made to an API should be given a UUID. This **SHOULD** be returned in the response to that request as a `x-request-id` header allowing the client to easily log and quote this value.

APIs **SHOULD** log this request ID, along with an other relevant information, such as the endpoint called, parameters and options and an indication of what was returned (an error, some data etc).

This information is invaluable when resolving bugs or issues that are reported.

Sources:

* [HTTP API Design - Support Caching with Etags - Interagent](https://github.com/interagent/http-api-design#trace-requests-with-request-ids)

### [x.x] Where appropriate, API logs  **SHOULD** be anonymous

Unless required, identifying information such as full IP addresses, location data, etc. **SHOULD** not be stored.

## Caching & version control

### [x.x] Where appropriate, API responses **SHOULD** be able to be cached

There are two forms of caching:

* *External* caching, caches Endpoint responses and can provide information even when the API itself is unavailable.
* *Internal* caching takes place the API application, e.g. query caching.

External caching is much more robust and effective than internal caching and should be used for APIs with large (thousands) of users. However this method of caching is only effective for anonymous requests, returning the same information. If authentication is used the effectiveness will be decreased.

Caching, of any kind, should only become a focus after an API has been launched and is proving, through metrics, to be causing performance problems. That said techniques that would make adding caching more difficult, such as a authenticating all methods, should be taken into consideration during development so as not to make adding caching more trouble than it needs to.

### [x.x] Where appropriate, APIs **SHOULD** use Etags for cached resources

Importantly the Etag for a resource **SHOULD** be the same regardless of the data-type used for the response.

Sources:

* [Rest Resources - Version Control for Entities section - Atlassian REST API Design Guidelines (V1)](https://developer.atlassian.com/display/DOCS/Atlassian+REST+API+Design+Guidelines+version+1#AtlassianRESTAPIDesignGuidelinesversion1-RESTResources)
* [HTTP API Design - Support Caching with Etags - Interagent](https://github.com/interagent/http-api-design#support-caching-with-etags)

### [x.x] Where appropriate, APIs **SHOULD** use sensible time limits for cached responses

Where caching is used suitable measures should be used to ensure stale or invalid data is removed in a trimly fashion.

Techniques such as `Cache-Control` headers can be used to instruct caching systems, and users, how long a response should be cached before a new request is made.

Users should be able to query this information in subsequent requests using a `If-None-Match` header.

For example, an Endpoint may update once an hour with a new ship position, responses from this endpoint should include a `Cache-Control` header to inform the user the information will not change until the next update. This also ensures any request made after this period has expired will automatically receive the updated information.

Sources:

* [Rest Resources - Version Control for Entities section - Atlassian REST API Design Guidelines (V1)](https://developer.atlassian.com/display/DOCS/Atlassian+REST+API+Design+Guidelines+version+1#AtlassianRESTAPIDesignGuidelinesversion1-RESTResources)
* [HTTP API Design - Support Caching with Etags - Interagent](https://github.com/interagent/http-api-design#support-caching-with-etags)

### [x.x] Where appropriate, APIs **SHOULD** use rate limiting to ensure the API is used fairly 

In some cases, for endpoints that may update frequently or which are expensive to process, rate limiting can be used to ensure users do not (inadvertently) overwhelm the API or cause performance/access problems for other users.

Where this type of activity apparent rate limiting can be used, to inform users they are making to many requests in a given period. This can be combined with technologies within the API to ensure this is enforced.

Sources:

* [HTTP API Design - Show Rate Limit Status - Interagent](https://github.com/interagent/http-api-design#show-rate-limit-status)

Resources:

* [Token Bucket - Wikipedia](http://en.wikipedia.org/wiki/Token_bucket)

## API requests

### [x.x]  API methods **MUST** be available at unique endpoints

Within these guidelines, an *endpoint* consists of 4 elements:

1. HTTP verb (e.g. `GET`)
2. HTTP headers (e.g. `Accept: application/json`
3. URL path (e.g. `/ships`)
4. URL parameters (e.g. `?operator=BAS`) 

The HTTP verb and URL Path **MUST** be specified in each API request (and indeed by HTTP itself), these are referred to as *required* elements.

HTTP headers and URL parameters can be specified in each API request, these are referred to as *optional* elements.

**An API endpoint is considered unique if its required elements are unique.**

For example,

* `[GET]V2/ships` and `[GET]V2/ships/{id}` are unique as the URL path is different.
* `[GET]V2/ship/{id}` and `[PUT]V2/ship/{id}` are unique as the HTTP verb is different.
* `[Get]V2/ships` and `[Get]V2/ships?id={id}` are NOT unique as the required endpoint elements are not unique.

This ensures each API endpoint can be bookmarked and referenced easily and that each API request refers to a unique API method, which is needed for analytics.

Sources:

* https://www.gov.uk/service-manual/making-software/apis.html#give-each-thing-a-bookmarkable-url
* [18F API Standards - API Endpoints - I8F](https://github.com/18f/api-standards#api-endpoints)

### [x.x] API endpoints **SHOULD** not change

Where endpoints do change location and perform the same function, use redirects (e.g. `301 Moved Permanently`) to ensure backwards compatibility. You **MUST NOT** do this if the method an endpoint refers to has changed, or where doing so would introduce confusion and ambiguity.
 
Sources:

* [APIs - Practice Service Evolution - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#practice-service-evolution)

### [x.x] API endpoints **SHOULD** use an appropriate HTTP verb

For example, mapping to CRUD these would be:

* `GET` for retrieving/reading
* `POST` for creating
* `PUT` for updateing
* `DELETE` for deleting

Sources:

* https://www.gov.uk/service-manual/making-software/apis.html#use-http-methods-as-tim-intended

### [x.x] API endpoints **SHOULD NOT** rely on HTTP verbs other than `GET` and `POST` 

A mechanism for using `POST` requests instead with some way specify the intended verb **SHOULD** be supported.

For example, a `_method` parameter could be used to fake other request types.

APIs **SHOULD NOT** use verbs such as **PATCH** which are unambiguous.
APIS **SHOULD** treat less common verbs with caution and **SHOULD** always a well supported alternative if used. 

Sources:

* https://www.gov.uk/service-manual/making-software/apis.html#use-http-methods-as-tim-intended

### [x.x] API endpoints **MUST NOT** allow `GET` requests to alter resources

`GET` endpoints should be *safe* and essentially act as read-only.

Sources:

* https://www.gov.uk/service-manual/making-software/apis.html#use-http-methods-as-tim-intended

### [x.x] API endpoints **SHOULD** be self descriptive

It **SHOULD** be possible to gather what an API method does from its endpoint alone. Therefore endpoints should be as self descriptive as possible, whilst being concise and ensuring endpoints remain well structured.

The easiest way to do this is to use descriptive and logical names for endpoints, you **SHOULD NOT** use verbs. If the method belongs to a resource use its name in its description.

Further endpoints **SHOULD** be structured logically and intuitively. Methods for a resource should be nested under the resource.

For example, `[GET]V2/ships/{id}/voyages` indicates the resource is `ships`, `{id}` the specific resource and the method is `voyages`. From this alone, it should be reasonably obvious this endpoint returns a list of voyages for a ship specified by `{id}`.

Sources:

* [18F API Standards - API Endpoints - I8F](https://github.com/18f/api-standards#api-endpoints)

### [x.x] API endpoints **SHOULD** be succinct

Ideally EndPoints should be snappy, URLs with more tokens require more effort to understand and increase the chance of making a mistake (in the spelling, order, etc.).

EndPoints do not need to reflect the underlying relationship between resources, providing this full relationship 'chain' is not relevant for the EndPoint.

The Interagent HTTP API Design guidelines provide a good example of when this technique makes sense. In this case there is no need to understand what the resources used are, other than their relationship (shown in the first URL example).

> "

    /orgs/{org_id}/apps/{app_id}/dynos/{dyno_id}

> Limit nesting depth by preferring to locate resources at the root path. Use nesting to indicate scoped collections. For example, for the case above where a dyno belongs to an app belongs to an org:

    /orgs/{org_id}
    /orgs/{org_id}/apps
    /apps/{app_id}
    /apps/{app_id}/dynos
    /dynos/{dyno_id}

> "

Sources:

* [HTTP API Design - Minimize Path Nesting - Interagent](https://github.com/interagent/http-api-design#minimize-path-nesting)

### [x.x] API endpoints **SHOULD** be case insensitive using hyphens as separators

This aids consistency and removes ambiguity, it also preserves compatibility with hostnames.

For example, `ships` not `Ships`, `cruise-reports` not `cruise_reports`.

Sources:

* [HTTP API Design - Downcase Paths and Attributes - Interagent](https://github.com/interagent/http-api-design#downcase-paths-and-attributes)

### [x.x] Where appropriate, API endpoints **SHOULD** use the plural term for a resource

The same endpoint **SHOULD** be used for both 'a thing' and 'a collection of things'. This helps keep URLs consistent as datasets change and are more predictable by not splitting methods over multiple URL paths.

For example, `[GET]v2/ships/{id}/` and `[GET]v2/ships` both use `ships` even though the first returns a single *ship* and the latter multiple *ships*.

You **SHOULD NOT** have URLs such as:

* `[GET]v2/ships/method_A`
* `[GET]v2/ship/method_B`
* `[GET]v2/ships/method_C`

Sources:

* https://www.gov.uk/service-manual/making-software/apis.html#give-each-thing-a-bookmarkable-url
* [HTTP API Design - Use Consistent Path Formats - Interagent](https://github.com/interagent/http-api-design#use-consistent-path-formats)

### [x.x] Where appropriate, APIs **SHOULD** support aliases for a resource

Typically IDs will be randomly assigned to resources, whether a numeric or UUID like ID is used. Whilst these ensure resources are uniquely referenced, they are not user friendly.

In many cases resources will contain one or more 'pseudo-IDs' such as a username or name that are usually unique for a resource, thus acting as an identifier, and are possible to remember or understand.

Where this is the case our APIs **SHOULD** support using these additional references as aliases to the same resource.

Aliases may not guarantee the correct resource will be returned, and in some cases may return more than one resource. A judgement should be made to ensure a balance between ease of referring to resources, and accuracy of results. Aliases which are likely to exhibit these problems **SHOULD** not be used.

Whilst supporting aliases does increase the complexity of an API, providing this behaviour is documented properly, there is no significant loss of clarity or  unambiguousness. Clearly there will be *some* loss which highlights the judgement aspect of this guideline. In general the cases where this behaviour **SHOULD** be used will be obvious. If in doubt, you **SHOULD NOT** use an alias.

For example, the call sign of BAS ship's are not likely to change, the call sign attributes id also an attribute by which a ship is commonly known. In this case it would be appropriate to use the ship callsign as an alias to a ship resource.

Sources:

* [HTTP API Design - Support Non-Id Dereferencing for Convenience - Interagent](https://github.com/interagent/http-api-design#support-non-id-dereferencing-for-convenience)

### [x.x] Where appropriate, URL parameters **MUST NOT** be required

URL Parameters (query strings) **MUST** be optional.

Generally URL parameters are used for filtering information in a request, for example setting sorting or specifying a date range. API requests made without these parameters would be the same in both cases, though in a different order or a super set of the same information.

Sources:

* https://www.gov.uk/service-manual/making-software/apis.html#give-each-thing-a-bookmarkable-url

### [x.x] Where appropriate, the order of URL parameters **MUST NOT** be significant

It **MUST NOT** matter in what order URL parameters are given.

For example,

`?from=1991-12-22&until=20010-07-21` and `?until=20010-07-21&from=1991-12-22` **MUST** return the same result if all other factors are the same.

Sources:

* https://www.gov.uk/service-manual/making-software/apis.html#give-each-thing-a-bookmarkable-url

### [x.x] Where appropriate, API endpoints which accept JSON **SHOULD** support serialised JSON within the request body

Where JSON is used for both the request and response data-type this provides a symmetry, simplifying making requests for the user.

This also prevents any errors when converting JSON data into HTTP form key-value pairs. This makes use the users code simpler and clearer without introducing ambiguity in our API.

For example,

    $ curl -X POST https://ships-api/V2/ship \
    -H "Content-Type: application/json" \
    -d '{"name": "RRS James Clarke Ross"}'

Sources:

* [HTTP API Design - Accept Serialised JSON in Request Bodies - Interagent](https://github.com/interagent/http-api-design#accept-serialized-json-in-request-bodies)

## API responses

### [x.x] API responses **SHOULD** use an appropriate status code

The general case, i.e. look it up if you don't know.

Its not practical to give guidance on specific status codes for every situation, look for the common consensus elsewhere.

4XX responses **SHOULD** be used to indicate client errors, i.e. that the user must fix
5XX responses **SHOULD** be used to indicate server errors, i.e. that we must fix

Sources:

* [18F API Standards - Error Handling - I8F](https://github.com/18f/api-standards#error-handling)

### [x.x] Where appropriate, API responses **MUST NOT** use a 2XX status code for an unsuccessful request

If the API is unable to return a response to a request that does not meet it documented output a non-2XX status code **MUST** be used.

For example, a request is made for a resource that cannot be found, the API is unable to return the expected output meaning a 2XX status code **MUST NOT** be used.

If, for the same request, the resource can be found but the resource has been deprecated, the API has been able to return the expected output, in addition to some additional information (that it is deprecated). In this case a 2XX status code **MUST** be used, and the additional information included in the request (i.e. as a warning).

Sources:

* [18F API Standards - Error Handling - I8F](https://github.com/18f/api-standards#error-handling)

### [x.x] Where appropriate, APIs **SHOULD** support CORS

CORS is an industry standard for allowing access to APIs from multiple origins from within web browsers. 

All major browsers, servers (including TomCat) and frameworks (including jQuery) support this standard and ensure strong security and wide interoperability.

Depending on how CORS is configured access can be restricted at the origin level. Outside of browsers these restrictions are meaningless (its just a header) but CORS provides good protection against certain web based attacks.

APIs **SHOULD NOT** use JSONP, its a hack and we **SHOULD NOT** condone its use. The 18F API Standards provide good reasons not to use this, they are echoed for convenience:

"JSONP is not secure or performant. If IE8 or IE9 must be supported, use Microsoft's XDomainRequest object instead of JSONP. There are libraries to help with this."

Sources:

* [18F -  - 18F](https://github.com/18f/api-standards#cors)
* [Why JSONP Is a Terrible Idea and I Will Never Use it Again - tmcw](https://gist.github.com/tmcw/6244497)

Resources:

* [Enable CORS](http://enable-cors.org/index.html)
* [Corslight - Mapbox](https://github.com/mapbox/corslite)

### [x.x] API responses **SHOULD** support appropriate data formats, defaulting to the simplest

The default format should the most useful for the given response. Where multiple data formats are offered, at least one should be a widely interoperable, ideally open, format.

Often more complex, specialised formats may be more useful for particular tasks. These should be offered, where feasible and based on user need, alongside simpler but more interoperable alternatives.

Sources:

* https://www.gov.uk/service-manual/user-centred-design/choosing-appropriate-formats.html

Resources:

* [List of common formats](https://www.gov.uk/service-manual/making-software/apis.html#representations-are-for-the-consumer)

### [x.x] APIs **SHOULD** use HTTP content negotiation to decide which supported data format to use

Content type (data type) negotiation using the `Accept` and `Content-Type` headers is a best practice which is widely supported and tested.

Sources:

* [Content Negotiation - Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Web/HTTP/Content_negotiation)

### [x.x] API responses **SHOULD** offer JSON as a supported data format

Where a single data format is offered this **SHOULD** ideally be JSON, unless another, similarly open format is available.

The 18F API Standards summarise the benefits of using JSON, they are echoed here for convenience:

"JSON is an excellent, widely supported transport format, suitable for many web APIs.

Supporting JSON and only JSON is a practical default for APIs, and generally reduces complexity for both the API provider and consumer."

Sources:

* [18F API Standards - Just Use JSON - I8F](https://github.com/18f/api-standards#just-use-json)

### [x.x] Where appropriate, API responses using JSON **SHOULD** use objects and underscored attributes in lower case 

Using an array to return data limits the ability to include metadata (including errors/warnings/notices etc.) and limits the ability to add additional top-level keys in the future.

Different languages use different case conventions. JSON uses underscored properties, and ensures attributes can be used without quotes in JavaScript.

For example, use `cruise_reports` not `cruise-reports` or `cruiseReports`.

Sources:

* [18F API Standards - Just Use JSON - I8F](https://github.com/18f/api-standards#just-use-json)
* [HTTP API Design - Downcase Paths and Attributes - Interagent](https://github.com/interagent/http-api-design#downcase-paths-and-attributes)

### [x.x] Where appropriate, API responses **SHOULD** return a full representation of a resource

This prevents additional requests (for example a POST followed by a GET request for the same resource), which reduces load on the API and improves the experience for the user.

Where a response may contain nested resources, judgement should be used whether to include all or part of each nested resource.

Wherever feasible nested resources **SHOULD** be returned in full, as requesting each nested resource separately would create significantly more requests than simply making the original request alone.

Sources:

* [HTTP API Design - Provide Full Resources Where Available - Interagent](https://github.com/interagent/http-api-design#provide-full-resources-where-available)

### [x.x] Where appropriate, API responses **SHOULD** nest related resources

For a resource contains relations to other resources these should be nested within the resource returned.

This guideline applies regardless of the number of attributes for each related resource are included.

The Interagent HTTP API Design guidelines provide a good example of why this technique makes sense.

> "
> E.g.

    {
        "name": "service-production",
        "owner": {
            "id": "5d8201b0..."
        },
        ...
    }

> Instead of e.g:

    {
        "name": "service-production",
        "owner_id": "5d8201b0...",
        ...
    }

> This approach makes it possible to inline more information about the related resource without having to change the structure of the response or introduce more top-level response fields, e.g.:

    {
        "name": "service-production",
        "owner": {
            "id": "5d8201b0...",
            "name": "Alice",
            "email": "alice@heroku.com"
        },
        ...
    }
> "

Sources:

* [HTTP API Design - Nest foreign key relations - Interagent](https://github.com/interagent/http-api-design#nest-foreign-key-relations)

### [x.x] Where appropriate, API responses **SHOULD** support pagination for managing large numbers of items

Where a response involves returning a large number of resources or other items pagination should be used to split these items into a number of 'chunks'. Only one chunk **SHOULD** be returned in each response, with additional requests used to request other 'chunks'.

The API **SHOULD** provide the mechanism for managing this process and communicating with the user using meta-data. This meta-data **SHOULD** include, where chunking has been used in a response, which chunk is present and how to request other chunks.

There are numerous implementations of pagination, most have similar features but expose these to the user in different ways. Some use HTTP headers whilst others data structures within response bodies themselves.

These guidelines don't make a preference as to which implementation **SHOULD** be used, and there is no fixed point where pagination need to be used. However any solution **SHOULD** allow the user to determine the size of each 'chunk'.

Pagination is often combined with sorting to return the most useful, as determined by the request, information first.

Sources:

* [HTTP API Design - Paginate With Ranges - Interagent](https://github.com/interagent/http-api-design#paginate-with-ranges)

Resources:

* [Ranges - Heroku Platform API](https://devcenter.heroku.com/articles/platform-api-reference#ranges)