---
date: 2016-12-27T01:12:41+01:00
title: Overview
type: index
---

## Shackbus in a nutshell

Shackbus is an opioniated specification on how to inter-connect devices within
an amateur radio station.

## Why we need Shackbus

Within an amateur radio station we have several devices which are
interconnected, mostly through hard wired with cables. Some vendors have
started to implement software interfaces, but they are incompatible amongst
each other.

Shackbus tries to solve this problem by providing common means of communication
and interfaces. Shackbus is leveraging open source, industry proven protocols
and services.

Shackbus is a collaborative effort and not owned by a person or commercial
entity. The Shackbus specification is published under the very permissive
[MIT License](http://choosealicense.com/licenses/mit).

## Key Technologies

### Transportation (MQTT)

For the transportation, Shackbus relies on Ethernet communications. However,
instead of using raw TCP or UDP sockets, Shackbus uses at its heart the TCP
based [MQTT protocol](http://mqtt.org).
[MQTT](http://mqtt.org) is a lightweight machine-to-machine (__M2M__)/
__Internet of Things__ connectivity protocol. It was designed as an extremly
lightweight publish/subscribe messaging transport.

### Message Protocol (Protocol Buffers)

[Protocol Buffers](https://developers.google.com/protocol-buffers/) is a
programming language neutral, platform-neutral, extensible mechanizm for
serializing structured data.

The following example shows how a message is defined in
[Protocol Buffers](https://developers.google.com/protocol-buffers/)'s Interface
Definition Language (IDL):

```protobuf
message Person {
    string id = 1;
    int32 id = 2;
    repeated string email = 3;
}
```