# Pragmatic REST
## For the Mojaloop Project

With the emergence of API strategy as a scaling tool for Internet service
businesses, the focus on interconnect technology has shifted. Building
on the principles that enabled the Web to form and scale, REST
(Representational State Transfer) has become a design preference for
Internet service APIs. But while the REST principles, proposed in Roy
Fielding's dissertation that defined them, have academic value as a
basis for research, a pure REST design is not at present practical for
most applications. We are advocating a kind of Pragmatic REST—a design
pattern that adopts the beneficial components of RESTful design without
requiring strict adherence to academic purity.

The Richardson Maturity Model
-----------------------------

Martin Fowler has referenced<sup>[1](#footnote1)</sup> a structured model of RESTful adoption
developed by Leonard Richardson and
[explained](http://www.crummy.com/writing/speaking/2008-QCon/act3.html)
at a QCon talk. Fowler refers to this as the Richardson Maturity Model
of RESTful design.

![Figure 1. Richardson Maturity Model of RESTful Design](https://GitHub.com/Mojaloop/docs/Wiki/Glory%20of%20Rest.png)

Martin Fowler, referencing [Rest in Practice](https://www.amazon.com/gp/product/0596805829?ie=UTF8&tag=martinfowlerc-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0596805829),<sup>[2](#footnote2)</sup>
summarizes the genesis of RESTful design:

> use Restful web services to handle many of the integration problems
> that enterprises face. At its heart . . . is the notion that the web is an
> existence proof of a massively scalable distributed system that works
> really well, and we can take ideas from that to build integrated
> systems more easily.

A pragmatic approach to RESTful design uses the best parts of Fielding's
conceptual framework to allow developers and integrators to understand
what they can do with the API as rapidly as possible and without writing
extraneous code.

At its most fundamental, a RESTful design is resource-centric and uses
HTTP verbs. At its most advanced, a design that follows pure academic
REST utilizes the HATEOAS principle by implementing Hypermedia Controls.
We are advocating a Level 2 RESTful design for Mojaloop.

Why not Hypermedia Controls?
----------------------------

Although HATEOAS is a fascinating principle-it advocates that a server
should respond to each client action with a list of all possible actions
that can lead the client to its next application state. And further,
clients *must not* rely on out of band information (like a written API
spec) for what actions can be performed on which resources or on the
format of URIs.

It is this final proscription that fails the test of Pragmatic REST:
While HATEOAS is an interesting theoretical approach to limit coupling,
it does not easily apply to Mojaloop (or any other contract
API design). When we take into account our audience for the interconnect
APIs, we find a group of commercial entities that will be operating
under a set of highly specific scheme rules. Interactions between the
participants, and between participant and central service hub, will be
highly specified to assign acceptable commercial risk that can be priced
at very low cost to end-users. This requires *ex-ante* predictability of
the API which is anathema to the HATEOAS principle defined by Fielding.

Pragmatic RESTful Principles
----------------------------

### URIs Define Resources

A well-designed URI pattern makes an API easy to consume, discover, and
extend, just as a carefully designed API does in a traditional
programming language. Pure REST disdains this principle in favor of
HATEOAS. But pragmatic REST follows a normal pattern for URI definitions to improve
human understanding, even if HATEOAS principles are employed for discovery. 

URI paths that refer to a collection of objects should consist of a
plural noun, e.g. /customers, to refer to a set of customers. When a
collection can have only one instance, the singular noun should be used
to avoid confusion. E.g. GET /transfers/:id/fulfillment is correct,
since there is only one fulfillment object per identified transfer.

URI paths that refer to a single object should consist of a plural noun
(representing the collection), followed by a predefined unique
identifier. E.g., /customers/123456 to refer to the specific customer
with number 123456. The identifier must be unique within the containing
collection and persist for the life of the object within that
collection. IDs must not be ordinal values-ordinal retrieval of objects
from a collection is possible using query parameters on the collection
URI.

URI paths may have a prefix to identify the environment, version, or
other context of the resource. Nothing should follow the identifying
path but collections and object references.

URI path and query segment identifiers should be chosen from the Roman
character set, \[0-9A-Za-z\]. Use *camelCase* to define the elements of
the URI path. Do not use snake\_case.

For the avoidance of doubt, “\_” (underscore) and “-” (hyphen) should
not be used in URI path or query segment identifiers.

This probably seems a bit parochial. The purpose is to find a
well-defined URI format that is consistent with wide-spread practice,
easy to define, predictable, and that maps to native environments and
conventions. It isn't going to satisfy everyone. Here is reasoning
behind this constraint:

CapitalCase and camelCase are the defacto standard for NodeJS and
JavaScript and are a common constraint in URI definition: URI path
segments are often mapped to JS internal resources and so conforming to
JS naming conventions makes sense.

Field names in JSON and SQL should also follow this convention since
they are often automatically mapped into variable name space and can be
referenced in URIs as path or query segment identifiers.

We should also avoid the use of “\$” unless it is required by a library
(e.g. JQuery). IBM JCL has passed away; let it rest in peace. There are
better scope control tools to separate name spaces than introducing
non-roman symbols.

We should avoid "-" (hyphen) in path segment and query parameter names
as it does not map into variable names, SQL, or JSON field name
identifiers.

Underscore characters must
be escaped in markdown source by prefixing each with a “\\” character.

Snake\_case has been reported to be slightly easier to read than
camelCase in variable names, but it actually does not improve
readability of URIs, as it visually interferes with path and query
segment delimiters making it difficult to visually parse them. And when URIs are 
underlined in presentation, the underscores become illegible.


### URI Parameters

Use a standard and predictable set of optional parameters in a
consistent way.

A set of standard query parameters should be used for collections to
enable caller control over how much of the collection they see. E.g.
"count" to determine how many objects to return, "start" to determine
where to start counting in the result set, and "q" as a generic
free-form search query. We will define the standard set of parameters as
we go and will apply them consistently.

### Verbs

Singular objects should support GET for read, PUT for complete
replacement (or creation when the primary key is specified by the client
and is persistent, e.g. a payment card PAN), and DELETE for delete.

Collections should support GET to read back the whole or part of a
collection, and POST to add a new object to the collection.

Singular objects may support POST as a way to change their state in
specified ways. Posting a JSON document to a singular object URI may
allow selected field values to be updated or trigger a state change or
action without replacing the whole object.

GET must be implemented in a *nullipotent* manner—that is, GET never
causes side effects and never modifies client-visible system state
(other than logging events or updating instrumentation, e.g.).

PUT and DELETE must be implemented in an *idempotent* manner—that is,
changes are applied consistently to the system data in a way that is
dependent only on the state of the resource and inputs but on nothing
else. The action has no additional effect if it is executed more than
once with the same input parameters and does not depend on the order of
other operations on a containing collection or other resources held in
the collection. For example, removing a resource from a collection can
be considered an idempotent operation on the collection. Using PUT to
fully replace (or create) a uniquely identified resource when the URI is
fully known to the client is also idempotent. This implies that the
system may reorder operations to improve efficiency, and the client does
not need to know whether a resource exists before attempting to replace
it.

POST and PATCH<sup>[3](#footnote3)</sup> are not idempotent operations. POST is used to create
new resources where the resource identifier is assigned by the server or
where a single identified internal resource is implied by the target URI
(e.g. POST /transfers, but PUT /transfers/:id/fulfillment).

### Data Format

We favor [JSON](http://json.org/)<sup>[4](#footnote4)</sup> related data formats over XML. In
some cases, data formats will be binary or XML, as defined by
pre-existing standards, and these will be precisely specified. Binary
formats should have a formal syntax to avoid ambiguous representational
translations (e.g. character set translations, big- or little-endian
representations of numeric values, etc).

Date and time values used in APIs should comply to the ISO 8601
standard, and further profiled by the w3c Note on Date and Time
Formats.<sup>[5](#footnote5)</sup> This w3c note should lead to the reduction in complexity
and error scope of communicating components that must exchange tangible
dates and times. There will be cases where we use non-ISO format date or
time as required by an external standard, e.g. ISO 7813 expiry dates.

Existing standard XML formats should have an XSD schema for the
acceptable subset profile used within the project. For particularly
complex data formats, we may use a common format profile translator to
map between our project subset of the standard format and the wire
format used by a standardized protocol (e.g.). This will limit coupling
to complex formats in a more maintainable way.

When specifying the PATCH action for a resource, we will use a
consistent patch document format (e.g. [JSON
Patch](http://jsonpatch.com/)<sup>[6](#footnote6)</sup>).

### Return Codes

Use HTTP return codes in a consistent way and according to their
standard definitions. The standard codes are defined in RFC 2616.<sup>[7](#footnote7)</sup>

### Machine Readable Error Format

The API should provide a machine readable error result in a well-defined
JSON format. {TBD whether to use a response envelope and how to format
errors, faults, and success envelopes. RESTful design relies on headers
to carry protocol-defined errors, debug info can also be carried in
headers. We should be clear on why we are using an envelope and how this
supports normal production communication between client and server.

### Versioning

API URIs should include a version identifier in the format v*M* as a
leading path element (where *"M"* is the Major component of the
multi-part version number). The API and its version identifier element
must conform to the [semantic versioning](http://semver.org/)<span
id="_Ref459290010" class="anchor"></span><sup>[8](#footnote8)</sup> 2.0 specification for API
versioning.

A client must specify the Major version number in each request. It is
not possible for a client to express a requirement for a specific minor
version.

The full API version number is specified in the response header (TBD)
for all successful and error responses.

While an API version contract will be influenced by Major, minor, *and*
patch levels, only the Major version number is a production API binding
element-that is, a production client cannot request a particular minor
version or patch level and a production server will not accept a URI
request that specifies these extra elements.

However, in pre-production environments, it is anticipated that some
combination of minor, patch, pre-release, and metadata suffixes would be
supported in client requests (as defined in *semver* <span
style="font-variant:small-caps;">\[3\]</span>) and *may* be expressed in
*pre-production* URIs to assist with development and integration
scenarios.

We May Need to Give REST a Rest
-------------------------------

As we design the interconnection APIs between components and between
participating systems, we may find API requirements that don't precisely
match the Pragmatic REST pattern defined here. We will evaluate these
case-by-case and make the best choice to support the project goals.

Non-Functional Requirements
---------------------------

As we develop the APIs, we will make consistent choices about
non-functional requirements to reinforce the project goals.

<a name="footnote1">1</a>: [http://martinfowler.com/articles/richardsonMaturityModel.html](Richardson Maturity Model), retrieved August 18, 2016.

<a name="footnote2">2</a>: [https://www.amazon.com/gp/product/0596805829](https://www.amazon.com/gp/product/0596805829?ie=UTF8&tag=martinfowlerc-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0596805829), retrieved August 18, 2016.

<a name="footnote3">3</a>: RFC 5789, *PATCH Method for HTTP*, <https://tools.ietf.org/html/rfc5789>, retrieved August 18, 2016.

<a name="footnote4">4</a>: *Introducing JSON*, <http://json.org/>, retrieved August 18, 2016.

<a name="footnote5">5</a>: <http://www.w3.org/TR/1998/NOTE-datetime-19980827>, retrieved August 22, 2016.

<a name="footnote6">6</a>: *JSON Patch*, <http://jsonpatch.com/>, retrieved August 18, 2016.

<a name="footnote7">7</a>: <https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html>

<a name="footnote8">8</a>: *Semantic Versioning 2.0.0*, <http://semver.org/>, retrieved August 18, 2016.
