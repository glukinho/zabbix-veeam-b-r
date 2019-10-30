# zabbix-veeam-b-r

**This template is no longer maintained and works BAD. Please use REST integration instead: https://github.com/glukinho/zabbix-veeam-rest**

Zabbix template for Veeam backup & replication jobs. Backup jobs and replication jobs are discovered separately, and each particular job is monitored.
Trigger rise when:
 - for backup job: last job was not successful 
 - for replication job: last 3 job checks was not successful (it means the jobs remains unsuccessful for 3 hours)

No additional files are to be deployed to Veeam host, only Zabbix agent.

Just assign the template to the Veeam B&R host and make ``Timeout = 30`` in ``zabbix_agentd.conf``.

Don't set discovery or items periods too low as PowerShell queries to Veeam are extremely slow, I don't know why.

Tested on Zabbix 3.4.3 and Veeam Backup & Replication 9.5 Update 3 on Windows Server 2012 R2.
