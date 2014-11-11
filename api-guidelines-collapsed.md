# API Guidlines

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
