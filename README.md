The arteria Design and Style Guide
==================================

## Introduction
Welcome to the arteria Design and Style Guide

## Contents 
* [Python](#python)
  * [Imports](#imports)
  * [Indentation](#indentation)
  * [Line length](#line-length)
* [Django](#django)
  * [Providing an API](#providing-an-api)
  * [URLs](#urls)
* [JavaScript](#javascript)
* [CSS](#css)

### Python
General Python related points.

#### Imports

#### Indentation

Indent by using 4 spaces. Never use tabs.

#### Line length

Wrap lines at 120 characters.

### Django
General Django related points that extends the Python guide.

#### Providing an internal API

If you implement an internal, per package API, follow this example below.

    from crm_targeting import targeting_api
    api = targeting_api.TargetingAPI()
    api.do_sth()


#### URLs

Do not use `_` in URLs, use `-` instead.

### JavaScript

### CSS



