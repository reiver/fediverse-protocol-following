# Fediverse Protocol: following

This document gives an overview the process used to follow someone (or something) on the Fediverse.

What it describes is the idealized process.

When a particular Fediverse software does _not_ implement a step described in this document, it is mentioned.

## Table of Contents
* Step 0: Actor
* Step 1: DNS SRV
* Step 2: Web Host Metadata
* Step 3: WebFinger
* Step 4: 

## Step 0: Actor

People on the Fediverse are identified with identifiers that look like these:

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

Here are a number of other examples:

| Actor                                 | Actor Name | Host                         |
|---------------------------------------|------------|------------------------------|
| `@joeblow@example.com`                | `joeblow`  | `example.com`                |
| `@janedoe@apple.banana.cherry.social` | `janedoe`  | `apple.banana.cherry.social` |
| `@dariush@changelog.ca`               | `dariush`  | `changelog.ca`               |
| `@malekeh@social.example.net`         | `malekeh`  | `social.example.net`         |
| `tom@apple.aaa`                       | `tom`      | `apple.aaa`                  |
| `dick@banana.bbb`                     | `dick`     | `banana.bbb`                 |
| `harry@cherry.ccc`                    | `harry`    | `cherry.ccc`                 |

Now on to the next step....

# Step 1: DNS SRV

The next step to follow someone on the Fediverse is —

Do a DNS SRV look-up on the **host** (you inferred in the previous), with **protocol** = `"tcp"` and **service** = `"webfinger",` to discover if the **WebFinger** is on this **host** or another **host**.

So, for example, if your actor identifier was:

> `@joeblow@example.com`

Then that means that the **actor name** and **host** is as follows:

| Actor                                 | Actor Name | Host                         |
|---------------------------------------|------------|------------------------------|
| `@joeblow@example.com`                | `joeblow`  | `example.com`                |

So then, a DNS SRV look-up on **host** = `example.com` with **protocol** = `"tcp"` and **service** = `"webfinger"` means we look-up `_webfinger._tcp.example.com.`

If something comes up, then that is the new value for **host** in the next step.
If nothing came up, then keep the same value for **host** in the next step.

