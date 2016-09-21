..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

==========================================
Example Spec - The title of your blueprint
==========================================

Include the URL of your launchpad blueprint:

https://blueprints.launchpad.net/

Refactor the doctor test script.

Problem description
===================

The current doctor test script has many adaptations to different installers and
inspectors. It's hard to read and develop for the developer. As more installers,
monitors and inspectors will to support in the future, the test script will
become massive and difficult to maintaince.

As a developer, i want to have the concise codes to maintain.

Proposed change
===============

Pick up each installer, monitor and inspector as independent module. As a new
installer will be support, add a new module to handle it.

Use python which is an object oriented to realize it. Don't modify the external
API for functest. 

Alternatives
------------

It also still can be realized by shell. But it is not an object oriented,
modular, extensibl.

Data model impact
-----------------

None

REST API impact
---------------

None

Versioning impact
-----------------

None

Other end user impact
---------------------

None

Developer impact
----------------

None

Implementation
==============

Assignee(s)
-----------

Primary assignee:
  dongwenjuan

Other contributors:
  None

Work Items
----------

* refactor the test script by different installers
* refactor the test script by different monitors
* refactor the test script by different inspectors
* the common function

Dependencies
============

* the OpenStack env deployed by different installers
* setup the different monitors in OpenStack env
* setup the different inspectors in OpenStack env

Testing
=======

* test in different installers
* test in different monitors
* test in different inspectors

Documentation Impact
====================

None

References
==========

None
