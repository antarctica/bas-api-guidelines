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
* Resource - [Similar to the concept of an object in object orientated programming](http://restful-api-design.readthedocs.org/en/latest/resources.html)
* Request - [A request for something, such as a resource made by a user](http://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol#Request_message)
* Response - [A reply to a request, such as a representation of a resource](http://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol#Response_message)
* CRUD - **C**reate, **R**etrieve (**R**ead), **U**pdate, **D**estroy (**D**elete).
* BASIS - British Antarctic Survey Information Services

Guidelines use a numbered prefix like this:

#### [X.X] Guideline

 e.g. 

####[2.4] Guideline

## Audience

These guidelines are aimed at API authors or those working closely with them, such as technical managers for APIs used in a project. You do not need to know these guidelines to consume an API based upon them. The documentation for the respective API **SHOULD** contain any information you require.

These guidelines are written for a technical audience and use technical terms where appropriate. The *Conventions & Terms* section will document any terms that may not be generally known by such an audience, or where a term is used to mean something other than its common definition.

## Feedback

**Feedback and discussion is strongly encouraged,** either formally through revisions to this document, or informally by contacting any of the authors.

## Acknowledgements

As noted later, **BAS APIs are not significantly unique**, therefore large parts of guidelines produced by others are directly applicable here. Consequently, large parts of these guidelines are based on other peoples work, namely.

* [Government Digital Service - Service Manual](https://www.gov.uk/service-manual)
* [18F - 18F API Standards](https://github.com/18f/api-standards)[1]
* [Interagent - HTTP API Design](https://github.com/interagent/http-api-design)[2]

[1] 18F are the US equivalent of the GDS.  
[2] AKA Heroku

## Aims & Objectives

The aims of these guidelines are:

* To ensure APIs created by BASIS follow best practice in a way that makes them easier to maintain and use.
* To ensure, where appropriate, APIs created by BASIS are of a consistent design with one another, so as to be able to share experience and efficiently maintain multiple APIs.

These aims will be achieved through these objectives:

* Provide a series of guidelines focusing on the *design* and *behaviour* of APIs[1].
* Promote the use of standards, best practice and how these create better APIs.
* Ensure technologies and approaches used to create APIs are justified.
* Provide, real world, non-abstract resources and implementations which creators can use to provide functionality that meet these guidelines[2].
* In some cases, make opinionated decisions, with explanations why these have been made.
* Ensure any relevant requirements that apply to BASIS through BAS, NERC, Government, etc. are followed.
* Ensure these guidelines are updated in a timely fashion to ensure guidance remains relevant and APIs remain useful.

[1] These guidelines provide one way of doing things, this is not the **only** way, and in some cases may not be the **best** way. In such cases, you **SHOULD** move away from these guidelines. However such APIs **MUST** state they do not follow these guidelines. You **MUST** be aware of the potential repercussions of doing this such as security and interoperability issues, etc. and manage these yourself.

[2] These are not required implementations, where others are more suitable they **SHOULD** be used.

## Scope

* Currently these guidelines apply to APIs created by members of BAS Information Services (BASIS) only.
* These guidelines apply to both **new** and **existing** APIs, which may require some existing APIs to be modified [1].
* These guidelines apply to both **internal** and **external** APIs. Internal in this case refers to APIs used solely within BASIS, BAS or NERC.
* These guidelines apply to HTTP based 'RESTful' APIs only. Web and data services in general are out of scope.
* The specific technology stack used within an API is out of scope. These guidelines provide criteria on how choices in technology **SHOULD** be made and how these **SHOULD** be justified, but do not specify what languages, frameworks, methodologies **SHOULD** be used.

[1] APIs where this cannot be achieved are still in scope of these guidelines, but can choose not to implement them. Such APIs **MUST** state whether they follow or no not follow these guidelines in their documentation. If an API does follow these guidelines it **MUST** indicate the version used. If an API does not follow these guidelines you **MUST** be of the potential repercussions of doing so, such as security and interoperability issues, etc. and manage these yourself.

## General Principles

### [1.1] APIs **SHOULD** be consistent but not uniform, using the most appropriate solution for each need

### [1.2] APIs **SHOULD** be as simple as possible

### [1.3] APIs **SHOULD** be clear and explicit in their operation, returning helpful errors 

### [1.4] APIs **SHOULD** make things as easy as possible, whilst remaining clear and consistent

### [1.5] APIs **SHOULD** be as resilient as possible

### [1.6] Where appropriate, APIs **SHOULD** use best practice for solving common problems

### [1.7] Where appropriate, APIs **SHOULD** be open, and made available publicly

### [1.8] Where appropriate, APIs **SHOULD** use established standards and open formats

### [1.9] Where appropriate, APIs **SHOULD** favour proven and open source alternatives over experimental or proprietary, alternatives

## Need Driven

### [2.1] APIs **MUST**  meet the needs of their users

### [2.2] APIs **MUST** allow user feedback, and this **MUST** be taken seriously

### [2.3] APIs **SHOULD NOT** be created in isolation, and we **SHOULD** use our own APIs 

## API Development

### [3.1] APIs **SHOULD** have a single owner responsible for its delivery and support

### [3.2] APIs **SHOULD** be loosely coupled

### [3.3] APIs **SHOULD** use source control

### [3.4] APIs **SHOULD** use issue tracking

### [3.5] APIs **SHOULD** be robustly tested

## API Design

### [4.1] APIs **SHOULD** use `UTF-8` for character encoding 

### [4.2] APIs **SHOULD** use `ISO 8601` and `UTC` for dates and times

### [4.3] APIs **SHOULD** use unique ids for resources

### [4.4] Where Appropriate, resources **SHOULD** use `created_at` and `modified_at` timestamps

## Documentation

### [5.1] APIs **MUST**  Provide End User Documentation

### [5.2] APIs **SHOULD** provide real world examples

### [5.3] APIs **SHOULD** provide developer documentation

### [5.4] APIs **SHOULD** be backed by a schema

## Versioning

### [6.1] APIs **MUST** use versioning using whole integers

### [6.2] API versions **SHOULD** map to major releases

###[6.3] The API version **MUST** be the first token in a URL path, prefixed by a "v"

### [6.4] APIs **MUST NOT** assume a version for requests that do not specify one

### [6.5] APIs **MUST** preserve backwards compatibility within a version

### [6.6] APIs **SHOULD** try to be compatible with older versions, providing they remain clear and unambiguous

### [6.7] Where appropriate,  APIs **SHOULD** support old versions

### [6.8] **SHOULD** APIs **SHOULD** be forwards compatible, providing they remain clear and unambiguous

## Security

### [7.1] APIs **MUST NOT** rely on 'security through obscurity'

### [7.2] APIs **MUST NOT** use non-standard cryptography

### [7.3] Where appropriate, APIs **SHOULD** allow anonymous access

### [7.4] Where appropriate, APIs **MUST** restrict access to sensitive information

### [7.5] Where appropriate, APIs **SHOULD** use common authentication sources

### [7.6] APIs **SHOULD** use HTTPS

### [7.7] Where appropriate, APIs **MUST** use HTTPS for sensitive information

###  [7.8] Where HTTPS is used, APIs  **SHOULD** reject HTTP requests

## Logging & analytics

### [8.1] APIs **SHOULD** collect information about itself to determine user needs and identify problems

### [8.2] APIs **SHOULD** log requests using an unique identifier

### [8.3] Where appropriate, API logs  **SHOULD** be anonymous

## Caching & version control

### [9.1] Where appropriate, API responses **SHOULD** be able to be cached

### [9.2] Where appropriate, APIs **SHOULD** use Etags for cached resources

### [9.3] Where appropriate, APIs **SHOULD** use sensible time limits for cached responses

### [9.4] Where appropriate, APIs **SHOULD** use rate limiting to ensure the API is used fairly 

## API requests

### [10.1]  API methods **MUST** be available at unique endpoints

### [10.2] API endpoints **SHOULD** not change

### [10.3] API endpoints **SHOULD** use an appropriate HTTP verb

### [10.4] API endpoints **SHOULD NOT** rely on HTTP verbs other than `GET` and `POST` 

### [10.5] API endpoints **MUST NOT** allow `GET` requests to alter resources

### [10.6] API endpoints **SHOULD** be self descriptive

### [10.7] API endpoints **SHOULD** be succinct

### [10.8] API endpoints **SHOULD** be case insensitive using hyphens as separators

### [10.9] Where appropriate, API endpoints **SHOULD** use the plural term for a resource

### [10.10] Where appropriate, APIs **SHOULD** support aliases for a resource

### [10.11] Where appropriate, URL parameters **MUST NOT** be required

### [10.12] Where appropriate, the order of URL parameters **MUST NOT** be significant

### [10.13] Where appropriate, API endpoints which accept JSON **SHOULD** support serialised JSON within the request body

## API responses

### [11.1] API responses **SHOULD** use an appropriate status code

### [11.2] Where appropriate, API responses **MUST NOT** use a 2XX status code for an unsuccessful request

### [11.3] Where appropriate, APIs **SHOULD** support CORS

### [11.4] API responses **SHOULD** support appropriate data formats, defaulting to the simplest

### [11.5] APIs **SHOULD** use HTTP content negotiation to decide which supported data format to use

### [11.6] API responses **SHOULD** offer JSON as a supported data format

### [11.7] Where appropriate, API responses using JSON **SHOULD** use objects and underscored attributes in lower case 

### [11.8] Where appropriate, API responses **SHOULD** return a full representation of a resource

### [11.9] Where appropriate, API responses **SHOULD** nest related resources

### [11.10] Where appropriate, API responses **SHOULD** support pagination for managing large numbers of items
