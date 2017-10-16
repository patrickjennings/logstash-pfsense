# logstash-pfsense
Logstash configuration for pfSense syslog events. Gives a nice dashboard
for displaying blocked events from the firewall.

Includes a modified from configuration found on the internet to work with the
latest pfSense release v2.4 and Elastic release v5.5.2.

# How to install
## pfSense
Enable remote logging in the pfSense web UI by going to:

Status -> System Logs -> Settings

In Remote Logging Options, check "Enable Remote Logging", and add your
remote Logstash server to the "Remote log servers". For example:

192.168.1.100:5140

Finally, check the "Everything" checkbox for "Remote Syslog Contents".

## Logstash
Edit conf.d/10-syslog.conf and change the host conditional on line 4 to be your
pfSense IP address if it is not the default 192.168.1.1.

Copy the contents of the conf.d and patterns directories to /etc/logstash/.

## Kibana
Import the visualizations.json and dashboard.json.
