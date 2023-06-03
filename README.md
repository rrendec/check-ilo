check-ilo
=========

Simple [Nagios](https://www.nagios.org/) plugin to monitor HPE ProLiant system
health status through iLO 4 or later, using the Redfish based RESTful API.

Compared to other solutions, this plugin connects directly to the iLO module,
aiming to be as lightweight as possible. It is best suited for simple deployments
where a small number of servers, potentially in different networks, are monitored.

## Prerequisites
* Python 3
* The [nagiosplugin](https://github.com/mpounsett/nagiosplugin) library

## Useful links
* [HPE iLO 4 API reference](https://hewlettpackard.github.io/ilo-rest-api-docs/ilo4/)
* [nagiosplugin library documentation](https://nagiosplugin.readthedocs.io/en/stable/)
* [SNMP based plugin from HPE](https://github.com/HewlettPackard/nagios-plugins-hpilo)
* [RESTful plugin from HPE](https://github.com/HewlettPackard/nagios-hpeilo-restful-extension)

The RESTful plugin from HPE is important as an example of using the iLO RESTful API.
It shows the paths/objects that are relevant for monitoring *individual* subsystems.
See `src/restful/nagios_hpilo_restful_engine.c` for details. This could be used to
improve check-ilo and provide more granular information.
