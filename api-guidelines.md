# API Guidlines

Version:

* **0.1.0** - November 2014 - Draft

Authors:

* [Felix Fennell](mailto:felnne@bas.ac.uk) (BASIS)

Status: 

* **These guidelines have not yet been adopted**. When they are, they will automatically become version 1.0.0.
* **Adopted versions** of these guidelines will be tracked in the **master** branch of the [API Guidelines repository](), tagged by version.
* **Draft versions** of these guidelines will be tracked in the **develop** branch of the [API Guidelines repository]().

## Conventions & Terms ##

**MUST** / **MUST NOT** - As defined by [RFC 2119](https://www.ietf.org/rfc/rfc2119.txt).

**SHOULD** / **SHOULD NOT** - As defined by [RFC 2119](https://www.ietf.org/rfc/rfc2119.txt).

Guidelines use a numbered prefix like this:

#### [X.X] Guideline

 e.g. 

####[2.4] Guideline

Important information is shown **like this**.

> Descriptive or explanatory information about a guideline is shown as a block quote like this.

## Audience

**These guidelines are aimed at API authors or those working closely with them**, such as a technical managers if an API is used with an project. **You do not need to know these guidelines to consume an API based on these guidelines**. The documentation for the respective API **SHOULD** contain any information you require.

**These guidelines are written for a technical audience and use technical terms where appropriate.** The *Conventions & Terms* section will document any terms that may not be generally known by such an audience, or where a term is used to mean something other than its common definition.

## Feedback

**Feedback and discussion is strongly encouraged,** either formally through revisions to this document, or informally by contacting any of the authors.

## Acknowledgements

As noted later, **BAS APIs are not significantly unique**, therefore large parts of guidelines produced by others are directly applicable here. Consequently, **large parts of these guidelines are based on other peoples work**, particularly those with significant experience.

* [Government Digital Service - Service Manual](https://www.gov.uk/service-manual)

## Aims & Objectives

The aims of these guidelines are:

* To ensure APIs created by BASIS follow best practice in a way that makes them better to maintain and use.
* To ensure, where appropriate, APIs created by BASIS are of a consistent design with one another, so as to be able to share experience and ease maintaining multiple APIs.

These aims will be achieved through these objectives:

* Provide a series of guidelines focusing on the *design* and *behaviour* of APIs[1].
* Promote the use of standards, best practice and how these create better APIs.
* Ensure technologies and approaches used to create APIs are justified.
* Provide, real world, non-abstract resources which creators can use to provide functionality that meet these guidelines[2].
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

#### [0.1] **APIs should be consistent but not uniform,** using the most appropriate solution for each need.

> Consistency, within these guidelines, refers to not only providing a similar response format, errors, etc. but also the *stability* (amount of change) and *sustainability* (long term maintenance and availability) of the API.

> This is the ninth GDS Design Principle and echoed below for convenience.

> "Wherever possible we should use the same language and the same design patterns â€” this helps people get familiar with our services. But, when this isn't possible, we should make sure our underlying approach is consistent. So our users will have a reasonable chance of guessing what they're supposed to do.

> This isn't a straitjacket or a rule book. We can't build great services by rote. We can't imagine every scenario and write rules for it. Every circumstance is different and should be addressed on its own terms. What unites things, therefore, should be a consistent approach â€” one that users will hopefully come to understand and trust â€” even as we move into new digital spaces."

> Wherever possible APIs should use consistent terminology and meaning, including field names, actions, etc. Wherever possible these should be commonly used terms used elsewhere.

> The *Sources & Further Reading* section has more resources on this guideline.

####[0.2] Wherever possible, **APIs should be developed in the open, and made available publicly**

> Given BAS is Government organisation (according to Wikipedia so it must be true) our work should visible and accessible. Providing APIs aids this by offering data in an organised, logic way in convenient formats, ideally without involvement with BAS staff.

> In addition to API outputs, the research, design and code of APIs themselves can prove useful to others and ourselves. We benefit enormously from the work of others, through open sourced ideas and technologies, it is therefore right we make whatever we can available for others.

> In general the more people that use our APIs, and able to see how they work, the higher the chance of feedback. Either bugs/inaccuracies in our code or data we can correct, or 'have you thought about this' type ideas.

> This is the tenth GDS Design Principle, the *Sources & Further Reading* section has more resources on this guideline.

####[0.3] **Proprietary, beta or experimental technologies should be avoided in favour of  proven, open source alternatives.** This ensures that APIs are more likely to be available for longer.

> A experimental or immature technology may be discontinued. If resources are not available to reimplement the features that technology provided, the API may be degraded or cease to function. Similarly, if proprietary technology is used and is no longer supported or open sourced, it will become obsolete and incompatible with newer technologies.

> Ongoing, variable licensing costs may force the removal of a proprietary technology. If resources are not available to reimplement the features that technology provided, the API may be degraded or cease to function.

> Each time a technology is changed it may introduce new dependencies and constraints, such as needing to remove a feature that the new technology cannot provide itself. New bugs may be introduced, potentially across the API. Such changes introduce change, which impact on the consistency of the API.

> The *Sources & Further Reading* section has more resources on this guideline.

####[0.4] **APIs SHOULD be *clear and explicit* in their operation, returning helpful errors.** 

> Documentation should provide clear information on:

> * Availability (Uptime), rate limiting 
> * Security
> * Data sources, accuracy and limitations 

> APIs **SHOULD NOT** try to 'guess' or make assumptions about what what the user wants. If a request doesn't make sense the API **SHOULD** say so by returning an error.  

> *Guessing* introduces unnecessary logic within the API, making it more complex, increasing the changes of something going wrong. This decreases reliability and increases unpredictability. However, APIs **SHOULD** be *helpful*.

> For example, an API method takes a start date as a filter for some dataset, the method expects a date in the form `YYYY-MM-DD`. A request is made using a date `2004/10/14`.

> This request **SHOULD** fail, stating the start date given is not recognised as valid.

> It is clear the date is valid, but is in the wrong format. Whilst it is possible (and likely trivial) to detect this and convert the date into the right format the API **SHOULD NOT** do so.

> In most cases, it would be necessary to add code to check for this, if the code is refactored and this is missed this request will now fail when previously it succeeded. This will likely have an impact on any service using the API and cause confusion (i.e. not clear and unambiguous) and require debugging. Further refactoring, probably caused by a submitted bug report, will then be needed to fix the error.

> In this case, the delimiter, `/` used is common and would typically be included in any *guessing* code. However if a `;` was used instead, and not coded for, that request would fail. This would mean the two requests, which contain the same fault, would be treated differently.

> Instead, a simple `if date == format` should be used, if it fails, for any reason, an error **SHOULD** be returned. The error **SHOULD** explain:
 
> * Why the request failed, possibly with links to documentation (the date wasn't valid)
> * The syntax that was expected (`YYYY-MM-DD`, e.g. `2004-07-23`)
> * The value used in the request ('2004/10/14')

> This shows, clearly and unambiguously, why the request failed and how to correct the mistake. Importantly, regardless of the input used, this method will, from first use, only succeed where the date is correctly formatted.

> The *Sources & Further Reading* section has more resources on this guideline.

####[0.5] **APIs SHOULD be as simple as possible.**

> Simple APIs, and code, are easier to understand than complex APIs and code. This increases the maintainability of the API, and through having 'less moving parts' creates fewer places for bugs to hide.

> Simple APIs are quicker to iterate on, document and release than more complex APIs. For users, it is easier and quicker to use a simple API, especially when revisiting implementations created in the past.

> APIs **SHOULD NOT** do more than they need to. If another service already provides a service we **SHOULD** use or recommend this, we **SHOULD NOT** duplicate it ourselves.

> For example, an API for providing the locations of BAS ships could include a current weather report from a third party. Since this weather information can be requested directly (rather than bundled by us) it **SHOULD NOT** be included in our API. Instead information on where to get this weather data from, and preferably an example, **SHOULD** be documented.

> Doing this keeps our API as simple as possible and lets us focus on making what we need to provide as useful as possible. We should let others concentrate on solving other needs.

> This is essentially the [UNIX philosophy](http://en.wikipedia.org/wiki/Unix_philosophy) i.e. 'do one thing and do it well', and the second GDS Design Principle.

> The *Sources & Further Reading* section has more resources on this guideline.

####[0.6] Where appropriate, **APIs SHOULD use established standards and open formats.**

> Good standards encourage interoperability through consistency between different systems implementing the same standards.

> Different standards target different *layers*, technologies or approaches used within an API. Conformance to appropriate standard, at whatever level, can be used to justify technology choices for example. In such cases it usually isn't necessary to verify a technology meets a standard but technologies that do (or claim to) **SHOULD** be preferred over those that don't.

> Following standards, or using standards compliment technologies, typically bring benefits such as community/hive knowledge (e.g. StackOverflow etc.) and compatibility with tooling, saving time and generally giving a better experience than non-standard alternatives.

> The [HTTP Protocol](https://tools.ietf.org/html/rfc2616) is a good example of a standard, using it means we can use a variety of tools (web browser, caching layers, load balancers etc.) and frameworks provided by others with a high confidence these will understand each other. End users will also typically understand, if not expect, the use of this standard. 

> Another, technology specific, good example, is the [PSR-4 Autoloader](http://www.php-fig.org/psr/psr-4/) standard for automatically loading PHP classes. Using this standard reduces the effort to use unfamiliar technologies, encouraging experimentation and making rapid iteration more achievable. Similarly a common standard encourages the creation of associated tooling, such as package managers and IDE/editor support.

> Data formats **SHOULD** be chosen based on there suitability to the data being represented and interpretability.

> Data formats are discussed later in this document, however in general, data formats should be as open as possible. Similar to technologies, proprietary data formats can become obsolete or expensive to maintain limiting their long term availability.

> The *Sources & Further Reading* section has more resources on this guideline.

####[0.7] Where appropriate, **APIs SHOULD use best practice for solving common problems.**

> **APIs SHOULD NOT 'reinvent the wheel'**. The types of APIs BAS will commonly create will not be unique. They therefore don't require unique functionality or solutions to common problems.

> Using a common solution can utilise prior or community knowledge, reducing implementation and support costs. Existing tooling, frameworks and can be easily applied, increasing interpretability and looser coupling between different solutions.

> For example, content negotiation for determining response format is a solved problem. Rolling our solution would take time, not cover all edge cases and would require all support to be provided by us. Using the *standard* solution means we benefit from the experience of others and more people are able to provide support (e.g. StackOverflow etc.).

> A distinction should be made between *best* practice, which should be followed, and *common* practice, which whilst widespread is not "a good idea". Examples of *common* practice which are justifiable to avoid include:

> * Solutions which break or mis-use standards.
> * Solutions which not sufficiently secure, in situations where a more secure alternative exists, or for sensitive information, where any solution exists.
> * Solutions which are 'hacks' or 'lazy' approaches, where a 'proper' approach is available, or rely on 'quirks' or 'side effects' to achieve their purpose.

> These approaches, especially the latter 'quirk' kind, are typically not sustainable as their behaviour could change at any time, often without warning. The results of this could, at best, break the approach used, or at worst, change the result of the approach. This could potentially suddenly introduce new security flaws or inadvertently exposing information presumed to be safe.

> A good example of a *common* solution is [JSONP](http://en.wikipedia.org/wiki/JSONP) which is essentially a hack so as not to use the *best* solution, [CORS](http://en.wikipedia.org/wiki/Cross-origin_resource_sharing).

####[0.8] Where possible, **APIs SHOULD be as resilient as possible**

Where we create APIs that rely on third parties we must ensure we have plans in place for where these services are either temporally or permanently unavailable in the future.

When evaluating whether to use an external service factors such as the reputation of the service, the cost (and if this likely to change), availability (can the service scale to the same degree we can) and support all need to considered. This applies both to external services provided internally (i.e. by ourselves, BAS, NERC) or by third parties.

These factors need to weighed against the importance of the functionality such services provide. For services providing core functionality, a more defensive, conservative approach should be followed.

It is unfeasible to provide all services ourselves, credit card processing for example **SHOULD** be left to a payment gateway, however we should create APIs in such a way that reliance on a particular service is abstracted. This ensures we can swap out services, potentially for newer, better ones, without having to change core 'business' logic. 

> The *Sources & Further Reading* section has more resources on this guideline.

## Need Driven

####[1.1] **APIs MUST be created to meet the needs of its users.**

> Ideally all stakeholders should be involved in the development of an API, including data providers, API creators, relevant project mangers, significant end users and representative users.

> For simple APIs, this may not be many people and simple to organise. Others may require more extensive research and engagement with users, including resolving conflicts through negotiation.

> Testing is important to ensure APIs we create meet these needs, and logging and monitoring should be used to track this over time. Feedback and retrospectives should be used to ensure that we don't repeat mistakes in the future, and support and emphasise things that worked well. 

> This is the first of the GDS Design Principles, the *Sources & Further Reading* section has more resources on this guideline.

####[1.2] **APIs MUST allow for feedback to be submitted by anyone and for this to taken seriously.**

> Ideally the individual responsible for each API should be contactable directly.

> Feedback **MUST** be treated seriously, particularly in regards to usability problems.  

> Examples of this type of feedback might include:

> * A user has made a reasonable attempt to achieve a task the API claims to support using provided documentation/examples and limited experimentation.
> * A user reports that something doesn't work as expected or is unclear how something should be used.
 
####[1.3] **We SHOULD use our own APIs** and, ideally, **they SHOULD NOT be developed insolation.**

> API creators SHOULD be also be API consumers, this is the quickest and easiest way to validate our APIs do what it should.

> API creators SHOULD also take part in any discussions on the needs of an API. This reinforces *why* the API is needed and helps ensures these needs are met.

> Wherever possible, APIs should be implemented in a real system, usually online. Again this highlights any problems in using an API and ensuring APIs are practical, if not *nice* to use.

> The *Sources & Further Reading* section has more resources on this guideline.

## Documentation & User Experience

####[2.1] **APIs MUST be well documented**

~~ Fill this out (the irony is not lost on me) ~~

* Availability (Uptime), rate limiting 
* Security
* Data sources, accuracy and limitations 
* Deprecation policy for older API versions

> The *Sources & Further Reading* section has more resources on this guideline.

####[2.2] **APIs SHOULD provide real world examples**

> In addition to through and accurate documentation, examples of how to make requests for different scenarios and responses which would be returned **SHOULD** be provided.

> This aids users in evaluating if the API will provide the information they are looking for, more so than verbose descriptions of responses.

> When implementing an API end users can use examples to get started quickly. Therefore examples **SHOULD** be functional (i.e. use a real ids) using safe, sensible defaults for real world, typical requests.

> Documentation **SHOULD** clarify any extreme values or lists of acceptable values, these **SHOULD NOT** be defined within examples.

> Examples **SHOULD** be runnable with a minimum of effort, ideally from the browser or the command line. Provision for features such as authentication/authorisation should be made, such as:

> * Use public methods (where available)
> * Use test credentials which may return fake data but sufficiently similar to read data to be useful for testing, e.g. give fake but realistic ship positions.
> * Show typical responses users can inspect to get a good idea what they would get.

> Complex APIs, where requests cannot be tested within a browser, **SHOULD** still offer some way to experiment. Commonly this is done using an API 'explorer' or 'playground'. In addition to self hosted solutions there are a number of SAAS options, though millage may vary in supporting complex APIs.

> The *Sources & Further Reading* section has more resources on this guideline. The *Resources & Implementations* section has read world examples of this guideline.

####[2.3] **APIs SHOULD make things as easy as possible, whilst remaining clear and consistent.**

> If there is something we can do to make things easier for the end user we should do so, providing this is clearly explained, either in the response or in documentation.

> This is Principle 4 of the GDS Design Principles, echoed here for convenience.

> "Making something look simple is easy; making something simple to use is much harder â€” especially when the underlying systems are complex â€” but that's what we should be doing.

> With great power comes great responsibility â€” very often people have no choice but to use our services. If we don't work hard to make them simple and usable we're abusing that power, and wasting people's time."

> The *Sources & Further Reading* section has more resources on this guideline.

## Method design

[URLS - points]

* URLs SHOULD be well structured, consistent, stable and clean, for both 'a thing' and 'a collection of things'.
* Query strings MUST NOT be required and MUST be used for optional, unordered parameters.

[URLS - sources]

* https://www.gov.uk/service-manual/making-software/apis.html#give-each-thing-a-bookmarkable-url

[HTTP methods - points]

* APIs SHOULD use appropriate verbs for CRUD actions
	* Get for Read
	* Post for Create/Update/Delete
	* Put for Update
	* Delete for Delete
* APIs MUST NOT allow Get requests to alter resources.
* Assume only Get and Post are available, i.e. use '_method' to fake a Put/Delete request
* APIs SHOULD NOT use ambiguous verbs such as Patch.
* APIs SHOULD treat less common verbs with caution, and always offer a well supported alternative.

[HTTP methods - sources]

* https://www.gov.uk/service-manual/making-software/apis.html#use-http-methods-as-tim-intended

## Security, Authentication & Authorisation

[Security - points]

* APIs MUST NOT roll their own crypto.
* Do not rely on security through obscurity.

[Security - sources]

* 

[HTTPS - points]

* HTTPS MUST be used for sensitive information.

[HTTPS - sources]

* [APIs - Be Public By Default - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#be-public-by-default)

[Authentication/Authorisation - points]

* Authentication/Authorisation SHOULD NOT require authentication/authorisation by default
	* Increases barriers
	* Makes examples harder

* Authentication/Authorisation MUST be used for sensitive information

* Avoid 'siloing' by using bespoke user accounts
	* For internal services integrate with NERC LDAP

* Wherever possible, APIs SHOULD use common authentication/authorisation schemes
	* Well supported, understood
	* More secure, higher chance of flaws being found and patched

The *Resources & Implementations* section has read world examples of this guideline.

[Authentication/Authorisation - sources]

* [APIs - Be Public By Default - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#be-public-by-default)

## Versioning

#### [X.X] APIs MUST use versioning, versions SHOULD map to major releases and MUST be whole integers

API versions are not alternatives, they are linear progressions, ideally improving over time. This means new API versions **SHOULD** replace older versions, therefore older versions **SHOULD** be deprecated.

#### [X.X] APIs MUST not assume a version for requests that do not specify one.

APIs **MUST NOT** use conventions such as `/latest/`, `/current/`, `/head/` etc. as pointers to the latest API version. This behaviour is not clear or unambiguous, requests made in this way may suddenly fail if a breaking change is introduced to a new version.

Instead users **MUST** explicitly state the version they wish to use. If no version is provided, the API **MUST** return a fatal error until one is provided.

#### [X.X] Within a version, APIs MUST preserve backwards compatibility

APIs **MUST NOT** introduce braking changes *within* an API version. If you need to do this create a new version.

Sources:

* [APIs - Practice Service Evolution - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#practice-service-evolution)

#### [X.X] Where possible, APIs SHOULD support old versions

It is not reasonable to assume all users will upgrade to newer API versions at the same time. Therefore old APIs **SHOULD** continue to be supported, for a limited period, to allow users to upgrade in their own time.

The length of this time period will depend on the audience of the API, for internal APIs the period can be quite short, for external APIs a longer period should be given. The number of users of the API should also be taken into account, which should be judged from API analytics and logs.

Wherever possible users **SHOULD** be notified of new API versions in advance, increasing the likelihood of a quicker adoption by allowing testing. Additionally, requests made to deprecated API versions **SHOULD** inform the user the version is deprecated and how they can use the new version.

APIs **SHOULD** clearly state their deprecation policy within their documentation, this allows users to evaluate if they can commit to this schedule before a version change occurs.

The number of API versions that should be supported will depend on the same factors as above and the rate at which new versions are released. Ultimately these are judgement calls with internal resources for supporting these older version being the limiting factor.

Supported, in these guidelines, mean older versions should remain accessible, bugs and faults should be addressed (as these will likely exist in newer versions as well). Security issues **MUST** be addressed, if this is not possible the older version MUST no longer be made available.

Improvements and new features, regardless of whether they maintain compatibility within a version, **SHOULD NOT** be supported in older versions.

Sources:

* [APIs - Practice Service Evolution - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#practice-service-evolution)

#### [X.X] APIs SHOULD try to remain compatible with older versions, providing they remain clear and unambiguous

For example, an API method is moved from `/ships` to `/fleet/ships` to be better organised, no other aspects of the method are changed.

This represents a breaking change, as requests made to `/ships` will no longer return what they did previously. In this case a request made to the earlier `/ships` and newer `/fleet/ships` will be identical (other than the URL obviously). Backwards compatibility can therefore be preserved by using a `301 Moved Permanently` header to redirect requests made to the old method to the new.

This remains clear and unambiguous by informing the user, 'this has moved to here', the user can then update their requests accordingly in their own time, which is nice.

Sources:

* [APIs - Practice Service Evolution - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#practice-service-evolution)

#### [X.X] Where possible, APIs SHOULD be forwards compatible, providing they remain clear and unambiguous

APIs should be designed to be robust and forward thinking, given the speed of evolution on the web.

For example, if a new header is added to later API versions older API versions should ignore it, rather than fail. Documentation should emphasise where different versions may give different responses for the same request, however these situations should be avoided where possible.

Sources: 

* [APIs - Practice Service Evolution - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#practice-service-evolution)

## Other

[X.X] One individual should take responsible for an API

* This person will be reasonable for making sure the API follows these guidelines.

[X.X] Data formats

* Responses **SHOUlD** be made available one or more appropriate data formats, with the simplest, most open, format used by default.

* Often more complex, specialised formats may be more useful for particular tasks. These should be offered, where feasible and based on user need, alongside simpler but more interoperable alternatives.

* Sources:

	* https://www.gov.uk/service-manual/making-software/apis.html#representations-are-for-the-consumer

		* Gives a list of common formats

	* https://www.gov.uk/service-manual/user-centred-design/choosing-appropriate-formats.html

		* General information

[Logging and Analytics - points]

* Collect how people use your API, this should aim to:
	* Detect bugs (errors, 404s, etc.)
	* Log usage (most popular requests, etc. identify needs, where to prioritise, need driven)
	* Log performance (queries, rendering time, caching performance, etc.)

[Logging and Analytics - sources]

* https://www.gov.uk/service-manual/making-software/apis.html#document-by-discovery-and-example
	* "Collect how people use your API"
* https://www.gov.uk/service-manual/making-software/apis.html#testing

[API Development - Points]

* APIs should be built in a loosely coupled way, using interfaces to separate tasks with specific implementations, and repositories to separate data sources from how and where that data is accessed.

* APIs should be tested, this takes a number of forms
	* Automated testing using linters, test suites & continuous integration, mocked services etc.
	* Human testing through passive and active feedback during alpha/beta/live stages of development

[API Development - Sources]

* https://www.gov.uk/service-manual/making-software/apis.html#code-integration
* https://www.gov.uk/service-manual/making-software/apis.html#testing

## Resources & Implementations

*This will probably be split into a wiki page*

[2.1]

Good examples

* [Stripe](https://stripe.com/docs/api)
* [New York Times](http://developer.nytimes.com/docs/read/article_search_api_v2)
* [Twilio](https://www.twilio.com/docs/api)

[2.2]

Self hosted

* [Swagger](https://helloreverb.com/developers/swagger)
* [Slate](https://github.com/tripit/slate)

SASS

* [Apiary](http://apiary.io/blueprint)
* [Mashape](https://www.mashape.com/)

Bespoke/Custom 

* [Facebook API Tools](https://developers.facebook.com/tools/)
* [Guardian API Explorer](http://open-platform.theguardian.com/explore/)
* [Google Search - API Explorer](https://www.google.co.uk/search?hl=en&q=API+explorer)

[Authentication/Authorisation]

* HTTP Basic authentication
* OAuth

[CORS]

* http://enable-cors.org/

## Sources & Further Reading

[0.1]

* [Ninth Principle - GDS Design Principles](https://www.gov.uk/design-principles#ninth)
* [APIs - Names Reinforce Conventions - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#names-reinforce-conventions)
* [Naming Principles - Microformats](http://microformats.org/wiki/naming-principles)

[0.2]

* [Tenth Principle - GDS Design Principles](https://www.gov.uk/design-principles#tenth)
* [APIs - Be Public By Default - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#be-public-by-default)

[0.3]

* [Choosing Technology - GDS Service Manual](https://www.gov.uk/service-manual/making-software/choosing-technology)
* [Technology Code of Practice - GDS Service Manual](https://www.gov.uk/service-manual/technology/code-of-practice.html)

[0.4]

* [APIs Explicitly Set Expectations - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#explicitly-set-expectations)

[0.5]

* [Keep It Simple Stupid (KISS) Principle](http://en.wikipedia.org/wiki/KISS_principle)
* [Second Principle - GDS Design Principles](https://www.gov.uk/design-principles#second)
* [APIs - Consuming and Using APIs - GDS Design Principles](https://www.gov.uk/service-manual/making-software/apis.html#consuming-and-using-apis)

[0.6]

* [APIs - Just Use the Web - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#just-use-the-web)
* [APIs - Choosing Appropriate Formats - GDS Service Manual](https://www.gov.uk/service-manual/user-centred-design/choosing-appropriate-formats.html)

[0.8]

* [APIs - Service Agreements and Resilience - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#service-agreements-and-resilience)

[1.1]

* [First Principle - GDS Design Principles](https://www.gov.uk/design-principles#first)
* [APIs - Testing - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#testing)

[1.3]

* [APIs - Build an API By Building With the API](https://www.gov.uk/service-manual/making-software/apis.html#build-an-api-by-building-with-the-api)

[2.1]

* [APIs - Explicitly Set Expectations - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#explicitly-set-expectations)
* [APIs - Practice Service Evolution - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#practice-service-evolution)

[2.2]

* [APIs Document by discovery... and Example - GDS Service Manual](https://www.gov.uk/service-manual/making-software/apis.html#document-by-discovery-and-example)

[2.3]

* [Fourth Principle - GDS Design Principles](https://www.gov.uk/design-principles#fourth)