---
title: Exists
---

Exists is an important keyword that returns `True` or `False` based on the
existence of the specified object. This is an important technique that lets you
test for existence before you test for a value and possibly incur an error. The
keyword has two slightly different typical uses. The first is to determine
whether a singular object specified by an inspector exists:

{% qna %}
Q: exists drive "c:"
A: True
{% endqna %}

{% qna %}
Q: exists drive "z:"
A: False
{% endqna %}

The above examples test for the existence of the specified objects on the client
computer. In these examples, you can see that the client has a drive `c:`, but
not a drive `z:`. Attempting to find out more about the non-existent drive can
generate an error. If you aren’t sure about the existence of an object, use the
`exist` keyword before you attempt to examine its properties.

The second usage is to determine whether a *plural* result contains any values: 

{% qna %}
Q: exists (files of folder "c:")
A: True
{% endqna %}

This expression returns `True`, because files exist in drive `c:`. Note that using
the plural property `files` is a safe way to refer to something that may or may
not exist. For instance:

{% qna %}
Q: file of folder "z:"
E: Singular expression refers to nonexistent object.
{% endqna %}

An error is generated here because there is no drive `z:` on the client
computer. If you ask for a plural answer:

````
files of folder "z:"
````

It doesn’t give you an answer, but it also doesn’t cause an error. Nevertheless,
both of these constructs can be examined with the `exists` keyword without
causing an error:

{% qna %}
Q: exists file of folders "z:"
A: False
{% endqna %}

{% qna %}
Q: exists files of folders "z:"
A: False
{% endqna %}

You can use existence to determine if two directories have any files in common
with an expression like this:

{% qna %}
Q: exists file (names of files of folder "c:\") of folder "c:\old C"
A: True
{% endqna %}

This expression creates inspector objects for each file in the `c:\` folder. It
then looks for a file of the same name in the folder `c:\old C`. It returns true
if there are any files with the same name.
