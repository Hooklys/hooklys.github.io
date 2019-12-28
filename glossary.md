---
layout: default
---

{% include nav.html %}

## Glossary


### Organizations

Organizations are the top level unit.

### Users

End user accounts.  

Users are granted permissions over organizations.


### Stacks

Owned by an organization.

Stacks are to be seen as webhooks distribution hubs.


### Webhooks

Hooklys receive them via Stacks.

They are the payloads being carried around between servers, including headers.

Typically in the form of xml or json, these can be arbitrary contain anything the sender desire to deliver. 

Webhooks record metadata from the original sender.
 

### Subscribers

Attached to Stacks, they are the configuration that dictate delivery logic of webhooks being received by stacks.

Subscribers control the information about the destination of delivery targets.  

There can be zero, one or multiple subscribers attached to a stack.


### Delivery schedule

When a stack receives a webhook, a delivery schedule will be automatically created.

These schedules will attempt to delivery the original payload to the target destination.

In case of failure, they are responsible to retry multiple times over a period of time.


### Delivery attempts

An attempt is the concrete execution of a schedule when a delivery is attempted.

Delivery attempt send the original webhook paylaod and headers to the target as described by the subscriber.

Delivery attempt record metadata from the target server response.

Multiple attempts will be attached to the same schedule in case of delivery failures.

