---
layout: default
title: Issue Lifecycle
nav_order: 4
---

# Issue Lifecycle

Issue or Pull Request is <a href="#new-issue">opened.</a><br>
Issue or Pull Request is <a href="#issuepr-assignment">assigned</a> to a Contributor.<br>
Contributor <a href="#fixing-and-closing-the-issuepr">fixes</a> the Issue or Pull Requests and closes/merges it.<br>
PM adds the Issue/PR to the Contributor's active Invoice.<br>

## New Issue

When a new Issue is opened, the PM will automatically put it into scope and look for
an assignee. The default role for any Issue is ``DEV`` and the default [estimation](#) is ``60 minutes``.
In the case of PRs, the role is ``REV`` (code reviewer) and the default estimation is ``30 minutes``.

If you don't want the Issue to be taken into scope, just add the ``no-task`` label when opening it and the PM
will not care for it.

## Issue/PR Assignment

The PM will look for a Contributor with the required role and assign it to them. If you want to assign it to a
specific Contributor, just assign the Issue/PR to the desired person and the PM will respect that. You have to
do this before the PM elects a Contributor -- once a ticket is assigned to someone, you cannot take it away from them.

However, keep in mind that assigning tickets manually is discouraged. It's always better to let the PM elect the
Contributor (for example, the PM will also check that the project has enough funds to pay them).

[Here](https://github.com/self-xdsd/self-core/issues/758) is an example of an Issue assigned automatically by the PM and [here](https://github.com/self-xdsd/self-core/issues/751) is an example of an Issue assigned manually.

## Fixing and closing the Issue/PR

Once assigned to a Task, a Contributor has ``10 days`` to fix it. If the deadline passes, the PM will take the Task away from
them and look for another assignee.

When the Issue is closed or PR is merged, the PM will add it to the Contributor's active Invoice.

[Here](https://github.com/self-xdsd/self-core/issues/751#issuecomment-737992552) is an example of successfully fixed Issue and
[here](https://github.com/self-xdsd/self-web/issues/183#issuecomment-733133357) is a missed deadline.
