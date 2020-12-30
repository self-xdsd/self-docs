---
layout: default
title: The Project Manager
nav_order: 3
---

# The Project Manager

The PM is a Github account which acts as a chatbot. Each Project is arbitrarily assigned
to one such PM.

The PM will only act automatically upon new issues - it will not do anything about the issues which
were opened prior to the Project's activation.

<a href="#webhook-events">Webhook Events</a><br>
<a href="#commands">Commands</a><br>
<a href="#timers">Timers</a><br>

## Webhook Events

When a Repo is activated, we set up a [Webhook](https://developer.github.com/webhooks/) so that Github notifies
the PM of certain events automatically. The PM will be notified of the following events:

* ``New Issue`` - so it can register new issues/pull requests as tasks.
* ``Reopened Issue`` - so it can register reopened issues/pull requests as tasks.
* ``Issue Comments`` - so it can execute and reply to commands.
* ``Push`` - so it can transform the latest ``TODO``s into new Issues.

## Commands

The PM can answer to a number of commands. To give a command, just add an Issue Comment addressed to the PM.
The comment must always start with the PM's tag.

For example: ``@charlesmike hello`` will prompt the PM to present itself.

* ``Hello`` -- any comment addressed to the PM containing the word **"hello"**.
* ``Status`` -- any comment addressed to the PM, containing the word **"status"**. The PM will respond with the Task's status, assignee, deadline etc.
* ``Resign`` -- a task's assignee can always resign from the task, if they cannot or simply do not want to solve it. The comment should be addressed to the PM and contain the word **"resign"**. Only the task's assignee can give this command.
* ``Deregister`` -- a task can be deregistered (taken out of scope) with a comment containing the word **"deregister"**. Only a Contributor with role ``PO`` or ``ARCH`` can give this command. When a task is deregistered, the task's assignee is automatically resigned.
* ``Register`` -- an Issue or PR can be registered as a Task with a comment containing the word **"register"**. Any Contributor can give this command.

The precedence of the commands is the same as the above order. For example, if a comment contains both **"hello"** and **"deregister"**, it will be unerstood as a ``Hello`` command.

## Timers

Besides listening to Webhooks and Issue Comments, the PM runs a few jobs regularly:

* The PM will review **new Issues/PRs every 10 minutes** and assign them to contributors.
* The PM will review the **assigned Tasks every 6 hours** and invoice them if their respective Issues/PRs are closed.
 This is also the time when the PM will look for another assignee if the Issue/PR is still open and the deadline is passed.
* The PM will try to pay all active Invoices once a week, on Monday. An Invoice has to have a total amount of at least **108,00 €** in order to be paid.
