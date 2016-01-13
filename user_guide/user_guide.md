# User and Programmer's Guide


## Introduction

CKAN is a powerful data management system that makes data accessible –
by providing tools to streamline publishing, sharing, finding and using
data. CKAN is aimed at data publishers (national and regional
governments, companies and organizations) wanting to make their data
open and available. It is also aimed at the data users who go to CKAN
instances in order to find open data and start using it.

## User Guide

Along with short guides spread throughout CKAN to describe each
individual page briefly, there is also a more detailed user guide in the
[official documentation]. The more detailed user guide goes through main
concepts and common processes such as uer registration.

## Programmer Guide

There are basically three ways to modify and adapt CKAN to ones needs:

-   CKAN extensions
-   CKAN themes
-   CKAN core

Each of these different ways is documented separately.

### Extensions

CKAN extensions is the most common and recommended way to modify and
adapt CKAN to ones needs. CKAN uses a plugin system where each CKAN
extension can hook into different parts of CKAN and modify the workflow
from there.

The [official documentation][1] is an in-depth resource on how to write
CKAN extensions, complete with tutorials, coding practices, test guides
and reference api.

### Themes

A CKAN theme is at its root a special kind of a CKAN extension. It
exposes and overwrites static files instead of hooking into a specific
method to change the workflow (technically it does hook into the
template loader but the code there is minimal).

CKAN uses the [Jinja2] template engine which has built-in template
extensions, so the most common way to theme CKAN is to provide new CSS
files, Javascript files and then extending specific theme files.

More details about themes can be found in the themeing guid in the
[official documentation][2].

### Core

In rare cases the core CKAN code needs to be changed. Most of the things
are done in extensions. However, CKAN is a free and open source software
project and anyone can help improve the core code base. There are also
often times when changes to the core code are needed to implement a
specific extension (or are general enough to warrant core code changes).
The general rule of thumb is to have the core code base as simple as
possible yet extendable via CKAN extensions, i.e. small core with lots
of flexibility.

For those who want to contribute to CKAN core, please refer to the
contribution guide which is a part of the [official documentation][3].

  [official documentation]: http://docs.ckan.org/en/latest/user-guide.html
  [1]: http://docs.ckan.org/en/latest/extensions/index.html
  [Jinja2]: http://jinja.pocoo.org/docs/templates/
  [2]: http://docs.ckan.org/en/latest/theming/index.html
  [3]: http://docs.ckan.org/en/latest/contributing/index.html
