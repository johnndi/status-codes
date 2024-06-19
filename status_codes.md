# STATUS CODES AND THEIR MEANINGS

HTTP response status codes indicate whether a specific HTTP request has been successfully completed. Responses are grouped in five classes:

## Informational responses (100 – 199)
****100 Continue**
This interim response indicates that the client should continue the request or ignore the response if the request is already finished.

**101 Switching Protocols**
This code is sent in response to an Upgrade request header from the client and indicates the protocol the server is switching to.

**102 Processing (WebDAV)**
This code indicates that the server has received and is processing the request, but no response is available yet.

**103 Early Hints**
This status code is primarily intended to be used with the Link header, letting the user agent start preloading resources while the server prepares a response or preconnect to an origin from which the page will need resources.

## Successful responses (200 – 299)
some examples are:

**200:** OK — Request successful, data returned.

**201:** Created — New resource created successfully.

**204:** No Content — Request successful, no data returned.

**205 Reset Content**
Tells the user agent to reset the document which sent this request.

**206 Partial Content**
This response code is used when the Range header is sent from the client to request only part of a resource.

**207 Multi-Status (WebDAV)**
Conveys information about multiple resources, for situations where multiple status codes might be appropriate.

**208 Already Reported (WebDAV)**
Used inside a <dav:propstat> response element to avoid repeatedly enumerating the internal members of multiple bindings to the same collection.

**226 IM Used (HTTP Delta encoding)**
The server has fulfilled a GET request for the resource, and the response is a representation of the result of one or more instance-manipulations applied to the current instance.
## Redirection messages (300 – 399)
some examples are:

**300: Redirection** — Additional action needed to complete request.

**301: Moved Permanently** — Resource permanently moved to a new URL.

**302: Found** — Temporary redirection to a different resource.

**304 Not Modified:** Used for caching; indicates the response has not changed, so the client can use the cached version.

**305 Use Proxy:** Deprecated; previously indicated that a response must be accessed through a proxy, but is no longer used due to security concerns.
**306 Unused:** Reserved for future use; no longer active.

**307 Temporary Redirect:** Redirects the client to another URI using the same HTTP method as the original request.

**308 Permanent Redirect:** Permanently redirects to another URI, requiring the same HTTP method as the original request.



## Client error responses (400 – 499)
these are:

**401: Unauthorized** — Authentication required but not provided.

**403: Forbidden** — Valid request, but no permissions to access.

**404: Not Found** — Requested resource cannot be found.

**410: Gone** — Resource is permanently unavailable.
411 Length Required: Request rejected because the Content-Length header is missing.

**412 Precondition Failed:** Server does not meet preconditions set by client headers.

**413 Payload Too Large:** Request entity exceeds server limits; server may close the connection or suggest a retry.

**414 URI Too Long:** Requested URI is too long for the server to interpret.

**415 Unsupported Media Type:** Server rejects request due to unsupported media format.

**416 Range Not Satisfiable:** Specified range in the request is outside the size of the target data.

**417 Expectation Failed:** Server cannot meet the expectation indicated by the Expect request header.

**418: I'm a Teapot** — Joke status code, not used practically.

**421 Misdirected Request**
The request was directed at a server that is not able to produce a response. This can be sent by a server that is not configured to produce responses for the combination of scheme and authority that are included in the request URI.

**422 Unprocessable Content (WebDAV)**
The request was well-formed but was unable to be followed due to semantic errors.

**423 Locked (WebDAV)**
The resource that is being accessed is locked.

**424 Failed Dependency (WebDAV)**
The request failed due to failure of a previous request.

**425 Too Early (Experimental)**
Indicates that the server is unwilling to risk processing a request that might be replayed.

**426 Upgrade Required**
The server refuses to perform the request using the current protocol but might be willing to do so after the client upgrades to a different protocol. The server sends an Upgrade header in a 426 response to indicate the required protocol(s).

**428 Precondition Required**
The origin server requires the request to be conditional. This response is intended to prevent the 'lost update' problem, where a client GETs a resource's state, modifies it and PUTs it back to the server, when meanwhile a third party has modified the state on the server, leading to a conflict.

**429 Too Many Requests**
The user has sent too many requests in a given amount of time ("rate limiting").

**431 Request Header Fields Too Large**
The server is unwilling to process the request because its header fields are too large. The request may be resubmitted after reducing the size of the request header fields.

**451: Unavailable for Legal Reasons** — Access prohibited due to legal issues.

## Server error responses (500 – 599)
**500:** Internal Server Error — General server error, cause unspecified.

**502:** Bad Gateway — Invalid response from an upstream server.

**503:** Service Unavailable — Server temporarily unable to handle requests.

**504:** Gateway Timeout — Upstream server response timed out.

**505 HTTP Version Not Supported**
The HTTP version used in the request is not supported by the server.

**506 Variant Also Negotiates**
The server has an internal configuration error: the chosen variant resource is configured to engage in transparent content negotiation itself, and is therefore not a proper end point in the negotiation process.

**507 Insufficient Storage (WebDAV)**
The method could not be performed on the resource because the server is unable to store the representation needed to successfully complete the request.

**508 Loop Detected (WebDAV)**
The server detected an infinite loop while processing the request.

**510 Not Extended**
Further extensions to the request are required for the server to fulfill it.

**511 Network Authentication Required**
Indicates that the client needs to authenticate to gain network access.