---
date: 2016-12-27T01:12:41+01:00
title: Overview
type: index
---

## About

Shackbus is an opioniated, vendor independent specification on how to
inter-connect devices within an amateur radio station.

## Purpose

Within an amateur radio station we have several devices which are
interconnected, mostly through hard wired with cables. Some vendors have
started to implement software interfaces, but they are mostly incompatible
amongst each other. Either because they use different transportation protocols
or have incompatible message protocols / formats.

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
lightweight __publish/subscribe__ messaging transport.

All clients connect to a centralized MQTT Broker which is typically located
(but doesn't necessarily) has to be in the Local Area Network.

Through the publish and subscribe architecture, connected clients publish and/
or subscribe to __topics__ relevant for them. Wildcard subscriptions are
possible.

The Shackbus specification comes with a recommended topic topology:

```
    station/class/device/specific
```

An Antenna switch for example would subscribe (listen) on the following topic:

```
    mystation/antennas/6pack/request
```

and publish (respond) on the following topics:

```
    mystation/antennas/6pack/response
    mystation/antennas/6pack/status
    mystation/antennas/6pack/error
```

### Message Protocol (Protocol Buffers)

[Protocol Buffers](https://developers.google.com/protocol-buffers/) is a
programming language neutral, platform-neutral, extensible mechanizm for
serializing structured data.

[Protocol Buffers](https://developers.google.com/protocol-buffers/) generates
a low-bandwidth optimized binary representation of the serialized data. Due
to the nature of it's binary format, different versions of the same message
are still compatible with each other. In other words: There is no need for
message versioning. This guarantees maximum compatibility amongst the different
services.

The content of a Protocol Buffers
[Protocol Buffers](https://developers.google.com/protocol-buffers/) message
is defined in easy understandable Interface Definition Language (IDL). The
following example shows the antenna switch's Request message in the
[Protocol Buffers](https://developers.google.com/protocol-buffers/)'s IDL:

```protobuf
message Request {
    repeated Antenna antennas = 1;
}

message Antenna {
    int32 id = 1;
    name string = 2;
}
```

All Shackbus messages can be found in the
[Shackbus ICD repository](https://github.com/Shackbus/message-icds) at
Github.com.

Protocol Buffers comes with a handy code generator which will create the
convenience methods and data structures for the specified IDL message.
Currently, the following programming languages are supported out of the box:

- C++
- C#
- Go
- Java
- Python
- PHP
- Ruby
- Objective C
- Javascript

There are many third party plugins available for other programming languages.

For pure ANSI C code generation check out:

- [nanopb](https://koti.kapsi.fi/jpa/nanopb/) for embedded devices (like
[Arduino](https://www.arduino.cc))
- [protobuf-c](https://github.com/protobuf-c/protobuf-c)


