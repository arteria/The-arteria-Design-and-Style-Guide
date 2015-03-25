# The arteria Design and Style Guide

## Introduction
Welcome to the arteria Design and Style Guide

## Contents
* [General](#general)
    * [Code Tags](#code-tags)
* [Python](#python)
    * [Encoding](#encoding)
    * [Imports](#imports)
    * [Indentation](#indentation)
    * [Line length](#line-length)
    * [Blank Lines and Whitespace](#blank-lines-and-whitespace)
    * [Comments](#comments)
* [Django](#django)
    * [Providing an API](#providing-an-internal-api)
    * [URLs](#urls)
    * [Best Practices](#best-practices)
* [JavaScript](#javascript)
* [CSS](#css)
* [HTML](#html)
    * [UX](#ux)

### General

Valid for all Languages and files.

#### Code Tags

##### `TODO`

    # TODO: implement the foo module here

##### `HACK` | `XXX`

    # HACK: this is bad and you should feel bad

##### `FIXME`

    # FIXME: works by now, but should be revised

##### `NOTE`

    # NOTE: see https://www.python.org/dev/peps/pep-0008/


### Python

This is not a complete Python style guide. In general we follow the [PEP 8 - Style Guide for Python Code](https://www.python.org/dev/peps/pep-0008/). Points discussed here are prefered by the arteria developer team.

#### Encoding

Add a magic comment to **all** python files to define the Encoding ([Source](https://www.python.org/dev/peps/pep-0263/)). Our default is **utf-8**.

    # -*- coding: utf-8 -*-

#### Imports

##### Multi-Line and Long Imports

It's ok to say:

    from django.contrib.auth.models import Permission, GroupManager

However if a line gets too long, avoid multi-line imports with backslash continuation or parentheses, we prefer to import the whole module.

    from django.contrib.auth import models

    models.GroupManager()

> **Note**: `import *` is never an option ;-)

##### Absolute and Relative Imports

We always prefer absolute imports.

##### Unused Imports

Delete unused imports immediately. If an import is required but unused mark it with `# NOQA`. Lines that contain a `# NOQA` comment at the end will not issue warnings in Flake8.

#### Indentation

Indent by using 4 spaces. Never use tabs.

#### Line length

Wrap lines at 120 characters.

#### Blank Lines and Whitespace

Separate top-level function and class definitions with two blank lines.

Method definitions inside a class are separated by a single blank line.

Use blank lines in functions, sparingly, to indicate logical sections.

#### Comments

Each line of a block comment starts with a # and a single space.

Inline comments should be separated by at least two spaces from the statement. They should start with a # and a single space.


### Django

General Django related points that extends the Python guide.

#### Providing an internal API

If you implement an internal, per package API, follow this example below.

    from crm_targeting import targeting_api
    api = targeting_api.TargetingAPI()
    api.do_sth()


#### URLs

Do not use `_` in URLs, use `-` instead.

#### Best Practices

##### Make use of `settings.USE_TZ`

    import time
    from datetime import datetime

    from django.conf import settings

    def _now():
        if settings.USE_TZ:
            return timezone.now()
        return datetime.now()


### JavaScript

.


### CSS

.


### HTML


#### Indentation

Indent by using 2 spaces. Never use tabs.


#### UX

##### HTML5 "input types"

`<input type="text">` was doing a decent job for decades, but now we have all sorts of inputs, "number" and "email" being the most beneficial ones. Here's the full list:

* `<input type="color">`
* `<input type="date">`
* `<input type="datetime">`
* `<input type="datetime-local">`
* `<input type="email">`
* `<input type="month">`
* `<input type="number">`
* `<input type="range">`
* `<input type="search">`
* `<input type="tel">`
* `<input type="time">`
* `<input type="url">`
* `<input type="week">`

##### Labels "for" checkboxes and radios

**Always** use a "for" label next to a checkbox or a radiobutton, so the user can click the text to change the "checked" state, not the little box. `<input type="checkbox" id="cb1"> <label for="cb1">` is the best practice.

##### Input text "placeholder"

Add placeholder text to your inputs.
