---
title: MISP 2.4.89 released (aka Event graph viewer/editor)
date: 2018-03-23
layout: post
banner: /img/blog/misp-small.png
---

A new version of MISP [2.4.89](https://github.com/MISP/MISP/tree/v2.4.89) has been released including a new MISP event graph viewer/editor, many API improvements and critical bug fixes (including security related bug fixes).

We introduced a new functionality allowing analysts and MISP users to view objects and attributes via a graphical visualisation. The event graph view supports the ability to edit objects, attributes and create relationships easily. We have foreseen a host of extensions to the event graph that we will be gradually adding in the future.

{{<video src="/img/video/event-graph.webm"  >}}

In addition to exporting in the STIX 2.0 format, MISP now supports the importing of STIX 2.0 data, directly from the UI. Significant improvements were made in the parsers for STIX 1.x and STIX 2.0 to support additional types of data. Don't hesitate to send us sample files which don't work as expected to help us improve our mapping. We have also added a warning in the import tool for the STIX import to describe that the STIX format can be lossy compared to the MISP standard format.

The API was significantly improved including changes such as attribute UUID in attribute level restSearch, deleteAttributes API can now mass-delete along with many other improvements.

Two security bugs were fixed:

- Sanitisation is now properly done from misp-modules especially to avoid XSS from potential malicious expansion modules. [CVE-2018-8948](https://cve.circl.lu/cve/CVE-2018-8948)
- An API integrity bug where an authenticated user could edit and overwrite an attribute without the UUID set. [CVE-2018-8949](https://cve.circl.lu/cve/CVE-2018-8949)

Another important fix was applied to the object handler to remedy a situation where under specific conditions could be overwritten. A recovery tool has been added in the diagnostics page.

Tons of bug fixes and minor improvement were added. [Changelog](http://www.misp-project.org/Changelog.txt) contains the complete list of what's changed from version 2.4.88.

We would like to thank all the contributors who have been fixing bugs, contributed new features or supported us for this release.

MISP [galaxy](/galaxy.pdf), [objects](/objects.pdf) and [taxonomies](/taxonomies.pdf) were notably extended by many contributors. These are also included by default in MISP. Don't forget to do a `git submodule update` and update galaxies, objects and taxonomies via the UI.
