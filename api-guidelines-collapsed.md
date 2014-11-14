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

### [x.x] APIs **SHOULD** be consistent but not uniform, using the most appropriate solution for each need

### [x.x] APIs **SHOULD** be as simple as possible

### [x.x] APIs **SHOULD** be clear and explicit in their operation, returning helpful errors 

### [x.x] APIs **SHOULD** make things as easy as possible, whilst remaining clear and consistent

### [x.x] APIs **SHOULD** be as resilient as possible

### [x.x] Where appropriate, APIs **SHOULD** use best practice for solving common problems

### [x.x] Where appropriate, APIs **SHOULD** be open, and made available publicly

### [x.x] Where appropriate, APIs **SHOULD** use established standards and open formats

### [x.x] Where appropriate, APIs **SHOULD** favour proven and open source alternatives over experimental or proprietary, alternatives

## Need Driven

### [x.x] APIs **MUST**  meet the needs of their users

### [x.x] APIs **MUST** allow user feedback, and this **MUST** be taken seriously

### [x.x] APIs **SHOULD NOT** be created in isolation, and we **SHOULD** use our own APIs 

## API Development

### [x.x] APIs **SHOULD** have a single owner responsible for its delivery and support

### [x.x] APIs **SHOULD** be loosely coupled

### [x.x] APIs **SHOULD** use source control

### [x.x] APIs **SHOULD** use issue tracking

### [x.x] APIs **SHOULD** be robustly tested

## API Design

### [x.x] APIs **SHOULD** use `UTF-8` for character encoding 

### [x.x] APIs **SHOULD** use `ISO 8601` and `UTC` for dates and times

### [x.x] APIs **SHOULD** use unique ids for resources

### [x.x] Where Appropriate, resources **SHOULD** use `created_at` and `modified_at` timestamps

## Documentation

### [x.x] APIs **MUST**  provide end user documentation

### [x.x] APIs **SHOULD** provide real world examples

### [x.x] APIs **SHOULD** provide developer documentation

### [x.x] APIs **SHOULD** be backed by a schema

## Versioning

### [x.x] APIs **MUST** use versioning using whole integers

### [x.x] API versions **SHOULD** map to major releases

###[x.x] The API version **MUST** be the first token in a URL path, prefixed by a "v"

### [x.x] APIs **MUST NOT** assume a version for requests that do not specify one

### [x.x] APIs **MUST** preserve backwards compatibility within a version

### [x.x] APIs **SHOULD** try to be compatible with older versions, providing they remain clear and unambiguous

### [x.x] Where appropriate,  APIs **SHOULD** support old versions

### [x.x] **SHOULD** APIs **SHOULD** be forwards compatible, providing they remain clear and unambiguous

## Security

### [x.x] APIs **MUST NOT** rely on 'security through obscurity'

### [x.x] APIs **MUST NOT** use non-standard cryptography

### [x.x] Where appropriate, APIs **SHOULD** allow anonymous access

### [x.x] Where appropriate, APIs **MUST** restrict access to sensitive information

### [x.x] Where appropriate, APIs **SHOULD** use common authentication sources

### [x.x] APIs **SHOULD** use HTTPS

### [x.x] Where appropriate, APIs **MUST** use HTTPS for sensitive information

###  [x.x] Where HTTPS is used, APIs  **SHOULD** reject HTTP requests

## Logging & analytics

### [x.x] APIs **SHOULD** collect information about itself to determine user needs and identify problems

### [x.x] APIs **SHOULD** log requests using an unique identifier

### [x.x] Where appropriate, API logs  **SHOULD** be anonymous

## Caching & version control

### [x.x] Where appropriate, API responses **SHOULD** be able to be cached

### [x.x] Where appropriate, APIs **SHOULD** use Etags for cached resources

### [x.x] Where appropriate, APIs **SHOULD** use sensible time limits for cached responses

### [x.x] Where appropriate, APIs **SHOULD** use rate limiting to ensure the API is used fairly 

## API requests

### [x.x]  API methods **MUST** be available at unique endpoints

### [x.x] API endpoints **SHOULD** not change

### [x.x] API endpoints **SHOULD** use an appropriate HTTP verb

### [x.x] API endpoints **SHOULD NOT** rely on HTTP verbs other than `GET` and `POST` 

### [x.x] API endpoints **MUST NOT** allow `GET` requests to alter resources

### [x.x] API endpoints **SHOULD** be self descriptive

### [x.x] API endpoints **SHOULD** be succinct

### [x.x] API endpoints **SHOULD** be case insensitive using hyphens as separators

### [x.x] Where appropriate, API endpoints **SHOULD** use the plural term for a resource

### [x.x] Where appropriate, APIs **SHOULD** support aliases for a resource

### [x.x] Where appropriate, URL parameters **MUST NOT** be required

### [x.x] Where appropriate, the order of URL parameters **MUST NOT** be significant

### [x.x] Where appropriate, API endpoints which accept JSON **SHOULD** support serialised JSON within the request body

## API responses

### [x.x] API responses **SHOULD** use an appropriate status code

### [x.x] Where appropriate, API responses **MUST NOT** use a 2XX status code for an unsuccessful request

### [x.x] Where appropriate, APIs **SHOULD** support CORS

### [x.x] API responses **SHOULD** support appropriate data formats, defaulting to the simplest

### [x.x] APIs **SHOULD** use HTTP content negotiation to decide which supported data format to use

### [x.x] API responses **SHOULD** offer JSON as a supported data format

### [x.x] Where appropriate, API responses using JSON **SHOULD** use objects and underscored attributes in lower case 

### [x.x] Where appropriate, API responses **SHOULD** return a full representation of a resource

### [x.x] Where appropriate, API responses **SHOULD** nest related resources

### [x.x] Where appropriate, API responses **SHOULD** support pagination for managing large numbers of items
