---
title: MISP 2.4.80 released (aka MISP objects release)
date: 2017-09-18
layout: post
banner: /img/blog/misp-small.png
---

A new version of MISP [2.4.80](https://github.com/MISP/MISP/tree/v2.4.80) has been released including the most awaited [MISP objects](https://github.com/MISP/misp-objects) feature along with other new features, security fix [CVE-2017-14337](https://www.circl.lu/advisory/CVE-2017-14337/) and improvements.

## MISP Objects

MISP now includes support for MISP objects. This allows MISP to support complex/combined objects in a flexible way along with their [relationships](http://www.misp-project.org/objects.html#_relationships) towards other objects or even attributes.

MISP objects already available by default are documented in [HTML](/objects.html) or [PDF](/objects.pdf).

The object model allows MISP users to add objects in addition to standard attributes to an event. Objects are composed of one or more attributes which are defined by the object templates.
The [object templates](https://github.com/MISP/misp-objects/tree/master/objects) are public and can be easily contributed to by everyone, allowing analysts, users and security professionals to build their own representation of various objects and share them back to their communities.

The default MISP object templates included are: ail-leak, cookie, credit-card, ddos, domain|ip, elf, elf-section, email, file, geolocation, http-request, ip|port, macho, macho-section, passive-dns, pe, pe-section, person, phone, r2graphity, regexp, registry-key, tor-node, url, vulnerability, whois, x509, yabin.

An example which describes a DGA (Domain Generation Algorithm) linked to two domain indicators using the MISP object functionality:

![DGA expressed as MISP object](/img/blog/DGA-in-MISP.png "{class='img-responsive'}")

Relationships can be described from an existing list of relationship types (e.g. `executed-by`, `impersonates`, `communicates-with`,...) or by values from your own relationship vocabulary. This allows to
model a fairly large set of cases from incident, collected intelligence, attacks or course-of-action to malware analysis.

Version 2.4.80 also includes an extended file import for binaries relying on [PyMISP](https://github.com/MISP/PyMISP/blob/master/pymisp/tools/create_misp_object.py) and [LIEF](https://lief.quarkslab.com/) to create parsed file objects for PE, ELF and MachOS binary formats.

We are expecting to see many creative uses of the new MISP object feature and improvements in the following weeks.

If you upgrade from an existing version of MISP, don't forget to do a `git submodule init && git submodule update` (or use the update in the UI) and restart the workers.

This release includes many bug fixes, improvements and new features.

The full change log is available [here](https://www.misp.software/Changelog.txt). [PyMISP change log](https://www.misp.software/PyMISP-Changelog.txt) is also available.

Don't hesitate to [open an issue](https://github.com/MISP/MISP/issues) if you have any feedback, found a bug or want to propose new features.

Don't forget our [MISP summit 0x3](https://2017.hack.lu/misp-summit/) before the [hack.lu](https://2017.hack.lu/) 2017 conference which will take place from 14:00 to 18:00, Monday 16 October 2017. The core team of MISP will also join the [hack.lu open source security software hackathon 0x2 ](https://hackathon.hack.lu/) which will take place 19-20 October 2017.

A new MISP training will take place in Luxembourg the 21st November 2017, [registration is now open](https://www.eventbrite.com/e/misp-training-november-edition-tickets-36347289722).
