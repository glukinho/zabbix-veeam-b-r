# zabbix-veeam-b-r

Zabbix template for Veeam backup & replication jobs. Backup jobs and replication jobs are discovered separately, and each particular job is monitored.
Trigger rise when:
 - for backup job: last job was not successful 
 - for replication job: last 3 jobs was not successful

No additional files are to be deployed to Veeam host, only Zabbix agent.

Just assign the template to the Veeam B&R host and make ``Timeout = 30`` in ``zabbix_agentd.conf``.

Don't set discovery or items periods too low as PowerShell queries to Veeam are extremely slow, I don't know why.

Tested on Zabbix 3.4.3 and Veeam Backup & Replication 9.5 Update 3.
