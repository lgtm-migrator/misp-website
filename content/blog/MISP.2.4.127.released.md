---
title: MISP 2.4.127 released (decay updates release edition)
date: 2020-06-19
layout: post
banner: /img/blog/decay.png
---

# MISP 2.4.127 released

A new version of MISP ([2.4.127](https://github.com/MISP/MISP/tree/v2.4.127)) has been released with an improved version of attributes decaying, new set of widgets, many improvements and bugs fixed.

# Improved decaying of attributes (version 2)

In MISP 2.4.116, a decaying functionality was added to allow users and organisations to easily expire information depending on their personalised objectives and targets.

Based on the feedback of the organisations relying on the decaying feature, the following improvements were included:

- Added a new user setting, `default_restsearch_parameters`, allowing users to supply restSearch parameters that will be automatically passed to the export mechanism during API queries fetch. The main purpose of this new setting is to enable users to inject filters when integrating with third-party tools not offering the possibility to control the queries performed against MISP. This for example allow to set the default decaying parameters to all restSearch queries performed by the given user.

- Added a new setting, `tag_numerical_value_override`, allowing users to override the `numerical_value` of tags. The main purpose of this new setting is to let users convey their own numerical values for tags. It does not constrain site-admins to the values provided by the official misp-taxonomy repositor, and instead allows them to define new values for entries not having a numerical value in the first place.

## Major changes in decay computation

Attributes' `last_seen` will now takes precedences over their `timestamp` if the former is set. In the decaying implementation prior to this version, if no sightings were recorded, the simulated last sighting was set on the `timestamp` value. However, in this new version, the `last_seen` value will be used instead. Users will be able to alter attributes (attach tags, modify `last_seen`, ...) without refreshing the decaying score to its maximum value.

# New widgets added to MISP

Additional widgets (contributed by Koen Van Impe) were added in MISP with the following features:

- Widget to display system resources (df, cpu, mem)
- Widget to display the latest sightings
- Widget to display the false positive sightings above certain threshold

Don't hesitate to contribute your own widgets and take a look at the existing ones.

# Various improvements

- [cli] Command for pulling from all remote servers.
- [UI] Add event ID to page table.
- [events:distributionGraph] Added close button in popover.
- [correlations] Refactored correlation saving.
  - Always show other correlating value (useful for CIDR correlations)
  - Make correlation saving faster (move more work to database, do not fetch not necessary fields)
  - Fix some small bugs

Many other improvements are documented in the [complete changelog is available](/Changelog.txt).

# Acknowledgement

We would like to thank all the [contributors](/contributors), reporters and users who have helped us in the past months to improve MISP and information sharing at large. This release includes multiple updates in [misp-objects](/objects.html), [misp-taxonomies](/taxonomies.html) and [misp-galaxy](/galaxy.html).

As always, a detailed and [complete changelog is available](/Changelog.txt) with all the fixes, changes and improvements.


