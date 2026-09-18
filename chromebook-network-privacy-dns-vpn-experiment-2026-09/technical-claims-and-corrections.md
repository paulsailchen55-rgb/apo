# Technical Claims and Corrections

## DNS over HTTPS

DNS-over-HTTPS encrypts DNS queries between the browser/client and the selected resolver. It addresses DNS-query visibility; it does not automatically make all browsing metadata invisible.

## VPN

A VPN can route traffic through a VPN provider rather than directly through the local network/ISP. This changes who is positioned to observe different portions of the connection. It is not equivalent to anonymous or invisible Internet use.

## Encrypted Client Hello

ECH is designed to protect particular information in TLS connection establishment, especially server-name information that could otherwise be exposed in the handshake, when the relevant client, server, and infrastructure support it.

It should not be described as a mechanism that completely blinds an ISP or hides every network fact.

## Chrome flags

Experimental browser flags can change behavior and may be removed or changed between Chrome versions. They should not be treated as permanent security controls without checking current browser documentation.

## "San Francisco" result

A location result associated with a network connection can describe an endpoint, routing location, data center, geolocation database result, or other infrastructure. It does not by itself demonstrate that a person is being watched.

## "Router blocked it"

Treat this as shorthand for an observed connectivity failure, not a diagnosis. Possible causes include DNS configuration, router policy, captive/network restrictions, VPN interaction, protocol incompatibility, browser behavior, service availability, or other technical faults.

## Preservation rule

Future claims should be labeled as user observation, measured result, documented technical fact, assistant interpretation, hypothesis, or unresolved question.
