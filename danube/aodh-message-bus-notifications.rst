..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

=============================
Aodh Message Bus Notifications
=============================

Vitrage would like to add Aodh alarms immediately via notification from the
message bus.

Problem description
===================

Currently Aodh datasource queries Aodh alarms periodically. It has a delay.
We would like to get notifications on Aodh alarm state changes from the
message bus, so they can be added to Vitrage immediately.

Proposed change
===============

Aodh `update_method` in vitrage config file will be configured with:
```
    [aodh]
    update_method = push
Add a new notification topic in Aodh config file: 
```
    [oslo_messaging_notifications]
    topics = vitrage_notifications

Vitrage listener will notify the Synchronizer upon a change in an Aodh alarm
definition or state.


Alternatives
------------

None

Data model impact
-----------------

None

REST API impact
---------------

None

Security impact
---------------

None

Pipeline impact
---------------

None

Other end user impact
---------------------

None

Performance/Scalability Impacts
-------------------------------

None


Other deployer impact
---------------------

** Config Aodh `update_method` as 'push' in vitrage config file.
** Add a new notification topic in Aodh config file.

Developer impact
----------------

None


Implementation
==============

Assignee(s)
-----------

Primary assignee:
  dongwenjuan <dong.wenjuan@zte.com.cn>

Work Items
----------

None

Future lifecycle
================

None

Dependencies
============

None

Testing
=======

Unit tests and tempest tests.

Documentation Impact
====================

None

References
==========

None
