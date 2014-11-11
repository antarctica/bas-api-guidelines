# API Guidlines

## General Principles

### [x.x] **APIs should be consistent but not uniform,** using the most appropriate solution for each need.

### [x.x] **APIs SHOULD Be as Simple as Possible.** ###

### [x.x] **APIs SHOULD be *clear and explicit* in their operation, returning helpful errors.** 

### [x.x] **APIs SHOULD make things as easy as possible, whilst remaining clear and consistent.**

### [x.x] Where possible, **APIs SHOULD be as resilient as possible**

### [x.x] Where appropriate, **APIs SHOULD use best practice for solving common problems.**

### [x.x] Wherever possible, **APIs should be developed in the open, and made available publicly**

### [x.x] Where appropriate, **APIs SHOULD use established standards and open formats.**

### [x.x] **Proprietary, beta or experimental technologies should be avoided in favour of  proven, open source alternatives.** This ensures that APIs are more likely to be available for longer.

## Need Driven

### [x.x] **APIs MUST be created to meet the needs of its users.**

### [x.x] **APIs MUST allow for feedback to be submitted by anyone and for this to taken seriously.**

### [x.x] **We SHOULD use our own APIs** and, ideally, **they SHOULD NOT be developed insolation.**

## API Development

### [x.x] APIs **SHOULD** Have a Single Owner, Who Is Responsible for Delivering and Supporting That API ###

### [x.x] APIs SHOULD Be developed in a Loosely Coupled Way

### [x.x] APIs SHOULD Be Developed Using Source Control ###

### [x.x] APIs SHOULD Be Developed Using Issue Tracking Software ###

### [x.x] APIs SHOULD be robustly tested

## Documentation

### [x.x] APIs **MUST**  provide end user documentation

### [x.x] **APIs SHOULD provide real world examples**

### [x.x] APIs **MUST** Provide Developer Documentation

### [x.x] **APIs **SHOULD** Be Backed by a Schema

## Versioning

### [x.x] APIs MUST use versioning, versions SHOULD map to major releases and MUST be whole integers

###[x.x] The API version **MUST** be the first token in a URL path, prefixed by a "v".

### [x.x] APIs MUST not assume a version for requests that do not specify one.

### [x.x] Within a version, APIs MUST preserve backwards compatibility

### [x.x] APIs SHOULD Try to Remain Compatible With Older Versions, Providing They Remain Clear and Unambiguous ###

### [x.x] Where possible, APIs SHOULD support old versions

### [x.x] Where possible, APIs SHOULD be forwards compatible, providing they remain clear and unambiguous

## Security, Authentication & Authorisation

### [x.x] APIs **MUST NOT** Rely on 'Security Through Obscurity'

### [x.x] APIs **MUST NOT** Use Non-Standard Cryptographic Methods for Encryption

### [x.x] APIs SHOULD Allow Anonymous Access Wherever Possible

### [x.x] APIs MUST Restrict Access to Sensitive Information Through the Use of Authentication and Authorisation ###

### [x.x] APIs **SHOULD** Use Common Sources of Authentication

### [x.x] APIs **SHOULD** use HTTPS by default

### [x.x] APIs **MUST** Use HTTPS for Sensitive Information

###  [x.x] Where HTTPS is used, HTTP requests **SHOULD** be rejected.

## Logging & Analytics

### [x.x] APIs **SHOULD** Collect Information to Determine User Needs and identify problems

### [x.x] Requests Should Be Logged, Using an unique Identifier

### [x.x] Request Logs  **SHOULD** Be Stored Anonymously ####


## Caching and Version Control

### [x.x] Where Possible, API Responses **SHOULD** Be Catchable

### [x.x] For Cached Resources, Etags **SHOULD** Be Used ####

### [x.x] For Cached Responses, Suitable Time Limits **SHOULD** Be Used ####

### [x.x] Where needed rate limiting **SHOULD** be used to ensure resources are not monopolised 

## API Requests

### [x.x] Each API method **MUST** be available at a unique *endpoint*

### [x.x] Wherever possible endpoints should remain as stable as possible.

### [x.x] APIs Endpoints **SHOULD** use an appropriate HTTP verb

### [x.x] API Endpoints **SHOULD NOT** rely on verbs other than `GET` and `POST` 

### [x.x] API Endpoints **MUST NOT** allow `GET` requests to alter resources.

### [x.x] API Endpoints **SHOULD** be self describing

### [x.x] Wherever Possible EndPoints **SHOULD** Be as Succinct as Possible

### [x.x] API EndPoints **SHOULD** Be Safe Insensitive and Hyphen Separated

### [x.x] For resources, API Endpoints **SHOULD** use the plural term in all cases

### [x.x] APIs **SHOULD** Support  Resources Aliases

### [x.x] URL Parameters **MUST NOT** Be Required

### [x.x] The Order of URL Parameters **MUST NOT** Be Significant

### [x.x] Serialised JSON should be accepted in request bodies using relevant HTTP verbs and where JSON is a supported data-type.

## API Responses

### [x.x] Each API Response **SHOULD** Use an Appropriate Status Code ####

### [x.x] a 2XX Status Code **MUST NOT** Be Used for Unsuccessful Requests ####

### [x.x] To Allow Access From Web Browsers, APIs SHOULD Use CORS

### [x.x] API Responses **SHOULD** Support Appropriate Data Formats, Defaulting to the Simplest.

### [x.x] APIs **SHOULD** Use Accept and Content-Type Headers to Agree on the Response Data Format

### [x.x] API Responses **SHOULD** Ideally offer JSON as an available data format

### [x.x] JSON API Responses **SHOULD** Use Objects With Lower Case, Underscored, Attributes 

### [x.x] API Responses **SHOULD** Use UTF-8 for Character Encoding 

### [x.x] API Responses **SHOULD** Use ISO 8601 for Dates, Times and Date-Times Using UTC ####

### [x.x] Resources **SHOULD** Use a Unique ID

### [x.x] Where Appropriate, Resources **SHOULD** Use Created and Modified Timestamps ###

### [x.x] Wherever Possible a Full Representation of a Resource Should Be Returned

### [x.x] API Responses Containing Related Resources **SHOULD** Be Nested

### [x.x] Where large numbers of items are to returned, pagination **SHOULD** be used