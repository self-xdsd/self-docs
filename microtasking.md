---
layout: default
title: Estimation and Microtasking
nav_order: 5
---

# Estimation and Microtasking

Each Issue has a default estimation of ``60 minutes``, while each PR has a default estimation of ``30min``.That's exactly how much the assignee will be paid upon completion.

<a href="#breaking-the-scope">Breaking the scope</a><br>
<a href="#example">Example</a><br>
<a href="#anatomy-of-a-todos">Anatomy of a TODO</a><br>
<a href="#changing-the-estimation">Changing the Estimation</a>

## Breaking the scope

Naturally, not any Issue can be resolved in 60 minutes. This is where **microtasking** comes into play. If the task is too big to be resolved within the estimation, the assignee should break it down into multiple tasks.

To achieve this, the assignee must solve the task **partially** and leave **TODO** comments in the code, which will be converted
into new Issues automatically by the PM. Later, when a **TODO** is removed from the code, the PM will close its Issue.

The newly created Issues will also have a default estimation of 60 minutes and the cycle should be repeated until finally the last Issue can be solved completely within the hour.

Consequently, any Pull Request should be small enough to be reviewable within 30 minutes.

## Example

[Here](https://github.com/self-xdsd/self-core/issues/717) is an example. The assignee was required to implement Gitlab's Issues within Self XDSD (by using Gitlab's RESTful API). It's obviously a big task, requiring at least several hours to complete. The assignee made a small [Pull Request](https://github.com/self-xdsd/self-core/pull/718) with the initial interfaces and classes and left **7 TODOs** in the code, which were transformed into [new Issues](https://github.com/self-xdsd/self-core/commit/f48613b20da5ced39b61277863a0e22c26e656f6#comments).

## Anatomy of a TODOs

Since TODOs are an important tool in microtasking, they have a certain grammar.
Here is how a TODO looks like:

```
@todo #123:60min This is a puzzle written while solving issue 123. We need to continue
 implementation with this and that. Do not forget to write unit tests and integration tests
 where applicable.
```

* ``@todo`` is the starting marker.
* ``#123`` is the originating ticket (the assignee was working on ticket ``123`` when they wrote it).
* ``60min`` is the estimation of the new task.
* Lines ``2..n`` must start with a space (must be alligned with the ``t``, not the ``@``).

TODOs may be written as code comments or JavaDocs in the code. Here is an example:

{% highlight java %}
/**
 * Issues in Github, GitLab or Bitbucket.
 * @todo #123:60min Continue adding methods to this interface.
 *  We will need at least methods open(...) and remove(...) which
 *  should open and remove an Issue respectively.
 */
public interface Issues extends Iterable<Issue>{

}

{% endhighlight %}

## Changing the Estimation

The default estimation can be overriden in two ways:

* Labels
* TODO estimation

You can label an Issue or PR with, for example, ``120 min`` and the PM will add this estimation.
Pay attention: the estimation cannot be changed after the ticket has been taken into scope.
So you have to add the label right when you open the Issue or PR.

When writing a TODO, the assignee can specify different estimations, for example ``45min``:

```
@todo #123:45min This is another todo written while solving issue 123. It's
 a smaller task, so the estimation is only 45 minutes.
```

The **minimum** allowed estimation is ``15 minutes``, while the **maximum** is ``360 minutes`` (6 hours).
