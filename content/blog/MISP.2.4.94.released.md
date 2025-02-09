---
title: MISP 2.4.94 released (aka summer improvements)
date: 2018-08-06
layout: post
banner: /img/blog/misp-small.png
---

A new version of MISP [2.4.94](https://github.com/MISP/MISP/tree/v2.4.94) has been released including an improved event graph interface, a new Elasticsearch plugin, various extensions and enhancements to the API, clean-ups and many improvements. Even though it's summertime, we continuously work on the MISP project and a lot of changes were introduced.

Major improvements have been implemented in the MISP event graph such as:

- Export functionality added in the MISP event graph to export in PNG, JPEG, JSON format and Graphviz dot format.
- Saving functionality to save the state of an event graph. This allows a user of an organisation to keep the state of the event graph and retrieve the history.

![New functionality in the MISP event graph to export the graph and save the state of the graph](/img/blog/save-graph.png "{class='img-responsive'}")

The MITRE ATT&CK matrix user-interface has been extended to add directly techniques at event level without passing by the galaxy interface.

A new functionality contributed allows users to log all MISP activities in Elasticsearch. It's pretty simple to configure thanks to its settings being part of the standard plugin settings system, so head over there to find the Elasticsearch configuration options.

![Configuring Elasticsearch with MISP](/img/blog/elasticsearch.png)

The CLI interface has been improved with the ability to get the API key of a given user, to force update the taxonomies, warning lists, notice lists and object templates. All of this serves to improve the automation of deployment of MISP instances without the need to use the UI.

MISP Synchronisation has been improved by moving the blacklist event skipping to the negotiation phase instead of first pulling blacklisted events and discard them after the fact. Synchronisation has also been improved in situations involving a large number of deletions. The pre-sync negotiation is now based on UUID-based lookups instead of relying on local IDs.

The MISP API has been introduced allowing users to deduce the prefered edit strategy of a given event. This has been introduced to help additional tools to decide whether to edit or extend MISP events. One such tool is TheHive project, which recently received a new release utilising the extend event functionality through this edit strategy API.

Various UI views have been improved to ease administration tasks for admins operating large MISP instances, including features such as listing the PGP fingerprints via the verifyGPG interface, a new statistic tab to show how many users/organisations were added over the past months/year and more.

Many internal changes and clean-ups were performed based on a recent static analysis of the codebase.

For a complete overview of all the changes, the full change log is available [here](https://www.misp.software/Changelog.txt). [PyMISP change log](https://www.misp.software/PyMISP-Changelog.txt) is also available.

New attribute types such as Monero (xmr) added along with the soft validation. [coin-address object template](https://github.com/MISP/misp-objects/blob/master/objects/coin-address/definition.json) updated to match the xmr attribute type.

Major changes in the STIX2 export and import were undertaken to improve the scope of the [MISP open standard](https://github.com/MISP/misp-rfc) and the mapping thereof to the STIX2 JSON format.

A huge thanks to all the [contributors](/contributors) who have tirelessly helped us improve the software and also all the participants in MISP trainings giving us a bunch of interesting feedback for improvements.

MISP [galaxy](/galaxy.pdf), [objects](/objects.pdf) and [taxonomies](/taxonomies.pdf) were notably extended by many contributors. These are also included by default in MISP. Don't forget to do a `git submodule update` and update galaxies, objects and taxonomies via the UI.

Don't forget that the MISP Threat Intelligence Summit 0x4 will take place the Monday 15th October 2018 before hack.lu 2018. Don't hesitate to have a look at our [events page](http://www.misp-project.org/events/) to see our next activities to improve threat intelligence, analytics and automation.
