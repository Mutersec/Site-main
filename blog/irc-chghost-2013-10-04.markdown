---
title: "IRCv3.2 CHGHOST Extension"
date: "2013-10-04"
---

The chghost client capability allows a server to directly inform clients about a
host or user change without having to send a fake quit and join. This capability
MUST be referred to as `chghost` at capability negotiation time.

When enabled, clients will get the CHGHOST message to designate the host of a
user changing for clients on common channels with them.

The CHGHOST message is one of the following:

    :nick!user@host CHGHOST user new.host.goes.here

This message represents that the user identified by nick!user@host has changed
host to another value. The first parameter is the user of the client. The
second parameter is the new host the client is using.

On irc daemons with support for changing the user portion of a client, the
second form may appear:

    :nick!user@host CHGHOST newuser host

If specified, a client may also have their user and host changed at the same
time:

    :nick!user@host CHGHOST newuser new.host.goes.here

This second and third form should only be seen on IRC daemons that support
changing the user field of a user.

In order to take full advantage of the CHGHOST message, clients must be modified
to support it. The proper way to do so is this:

1. Enable the chghost capability at capability negotiation time during the
   login handshake.

2. Update the user and host portions of data structures and process channel
   users as appropriate.

## Examples

In this example, `tim!~toolshed@backyard` gets their username changed to `b` and
their hostname changed to `ckyard`:

    :tim!~toolshed@backyard CHGHOST b ckyard

In this example, `tim!b@ckyard` gets their username changed to `~toolshed` and
their hostname changed to `backyard`:

    :tim!b@ckyard CHGHOST ~toolshed backyard

## Errata

A previous version of this specification did not include any examples, which made
it unclear as to whether the de-facto `~` prefix should be included on CHGHOST
messages. The new examples make clear that it should be included.