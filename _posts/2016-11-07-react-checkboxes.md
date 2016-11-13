---
layout: post
title:  "Unique IDs in Node for React"
date:   2016-11-07 10:28:59 -0700
categories: unique id react
---

I began a new project with React recently and encountered
a problem with adding an ID to
a form label linked to a checkbox. Suggestions to use
an incrementing counter were ok, but some kind of random
and unique ID seemed much better.

That's where UUIDs come into play. Node has a handy dandy
[package called UUID](https://www.npmjs.com/package/uuid) that
we can use.

The `v1()` function generates a time-based unique ID and the
`v4()` generates a random ID. `v4()` will do nicely here.

Then, to render your label:

~~~~
var uuid = require('uuid');

render() {
  const id = uuid.v4();
  return (
    <div>
        <input id={id} type="checkbox" />
        <label htmlFor={id}>label</label>
    </div>
  );
}
~~~~

Hurray! No more "unique ID required" errors!
