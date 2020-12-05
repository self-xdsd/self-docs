---
layout: default
title: Core Idea & Concepts
nav_order: 2
---

# Core Idea

The user signs in using their Github account and activates their ``Repo``. Once activated,
the repo becomes a ``Project`` and is assigned to one of Self's chatbot ``Project Managers``. The PM will start taking care
of it automatically: assign/unassign Issues, make payments, open/close Issues based on TODOs, listen to commands etc.

However, before the chatbot PM can actually do anything valuable, the Project needs to have some ``Contributors``.
After activating the Repo, the user must register some ``Contracts`` (a Contract is the bond between a Project and a Contributor).

# Concepts

<a href="#user-contributors">User, Contributors</a><br>
<a href="#repo-project">Repo, Project</a><br>
<a href="#task">Task</a><br>
<a href="#invoices">Invoices</a><br>
<a href="#payout-methods">Payout Methods</a><br>


## User, Contributors

A ``User`` is usually someone who activated one or more of their repos on Self XDSD. The Project Owner, if you wish.

A ``Contributor`` is a Github user who has a ``Contract`` with the ``Project``. A ``Contributor`` may have multiple
contracts with the same ``Project`` (one contract with the ``DEV`` role, another one with the ``ARCH`` role etc).

Of course, a person can be both a ``User`` and a ``Contributor`` -- that is, you can have your own repos managed by Self and also
work as a Contributor in other people's projects.

## Repo, Project

We call a ``Repo`` any Github repository owned by the authenticated user, which is not yet managed by Self.

A ``Repo`` which has been activated (it is now managed by Self), is called a ``Project``. This is a ``1:1`` relationship,
there can be only one ``Project`` for any Github ``Repo``.

## Task

A ``Task`` is the Self entity representing a Github Issue or PR which is managed by the PM. The basic life-cycle of an Issue/PR is the following:

- Issue/PR is opened;
- PM takes it into scope (registers a ``Task`` for it) **automatically**;
- PM assigns it to a Contributor;
- Contributor works on it and finally closes it;
- PM adds the Task to the Contributor's active Invoice and takes it out of scope.

Any Issue or PR will automatically become a ``Task``. If, for any reason, you don't want it to be a task,
you can just [say](/projectmanager.html#commands) ``deregister`` and the PM will remove it from scope (no payments will be made and the PM will charge no commission). Also, when opening a new Issue or PR you can label it ``no-task`` and the PM will **not** register it as a Task at all.

## Invoices

Tasks finished and closed by a Contributor are added to the Contributor's active ``Invoice``. The active Invoice is the latest, unpaid Invoice.

Invoices are automatically paid out regularly. Using the Project's active ``Wallet``.

## Wallets

Each Project can have a number of wallets attached, but only one of them can be active -- the one Self uses to make payments.

Each Project starts with a ``Fake Wallet`` attached to it: as long as this fake wallet is active, all the payments (including Self's commission) are fictive.

The user can register a ``Real Wallet`` and can specify a cash limit that Self is allowed to take from it. Real wallets are implemented using [Stripe](https://stripe.com).

## Payout Methods

Once a Project has a real wallet, the Contributors must create a ``Payout Method`` in order to be paid.
Payout methods are also implemented via [Stripe](https://stripe.com).

If the project has no real wallet, Contributors do not need to do anything, since the payments are fictive.
