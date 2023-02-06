# Fediverse Protocol: following

This document gives an overview the method used to follow someone (or something) on the Fediverse.

What it describes is the idealized method.

When a particular Fediverse software does _not_ implement a step described in this document, it is mentioned.

## Table of Contents
* Step 0: Actor
* Step 1: DNS SRV
* Step 2: Web Host Metadata
* Step 3: WebFinger
* Step 4: 

## Step 0: Actor

People on the Fediverse are identified with indentifiers that looks like these:

* `@joeblow@example.com`
* `@janedoe@apple.banana.cherry.social`
* `@dariush@changelog.ca`

There are 2 parts of these identifiers —

1. actor name, and
2. host.

Let's take a look at an example to help make this clearer:

```
  @dariush@changelog.ca
   \--+--/ \-----+----/
      |          |
actor name      host
```
In this example —

* the **actor name** is `dariush`, and
* the **host** is `changelog.ca`

Let's look at another example:

```
  @joeblow@example.com
   \--+--/ \----+----/
      |         |
actor name     host
```
In this example —

* the **actor name** is `joeblow`, and
* the **host** is `example.com`



