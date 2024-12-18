# Cleaning up

## Why?

- To verify which resources are still used, and track their up to date status
- To get rid of useless alerts which otherwise would pollute our night shifts
- To free up CPU/Space, thus reducing overall energy consumption and saving costs
- To fight against attack vectors and vulnerabilities
- To make sure that our sources stay tidy and reliable, helping your colleagues
- To learn more about your company internals and customers
- To accept to let go of useless stuff, and move forward
- To get an easy dopamine fix from doing something positive

## What to clean up?

You can clean up pretty much anything, here are some examples:

- Check the IPAM, look for traces from racktables migration (search for racktables). Check the IP ranges public and private, identify the locations of VMs, make sure that devices are in their proper category.
- Check Gitlab repositories. Archive anything that’s not used anymore, merge some repos with similar purposes, remove dead branches, update documentation about the purpose of each project
- Check monitoring. Remove active alerts from oncall, get rid of disabled hosts in Zabbix. Remove decommissioned nodes. Remove useless triggers
- Check the Stargate. Try connecting to hosts, make sure they are still reachable. Dig into the documentation to find the purpose of each host, check in netbox to make sure it is properly referenced. Remove if unused, or at least notify the team about a useless host that is still present, move it to /etc/stargate/old_servers
- Check sshportal. Remove unused/down hosts. Check that all team members have the correct group permissions
- Check grafana. Remove unused organisations. Fix or remove dead graphs. Fix missing metrics.
- Check the cmdb. Remove dead hosts, collect info about missing hosts.
- Check Confluence. Archive dead pages. Merge pages with similar purpose. Rename, improve pages by reading them once again, and take the time to understand the meaning of each page. Add hyperlinks and keywords to pages to make them easier to search for. Add diagrams whenever possible
- Check Passbolt. Remove dead passwords. Check the strength of existing passwords, notify and or improve passwords where possible and update them in Netbox. Make sure passwords are working. Add backdoor passwords to existing VMs when applicable.
- SSH into hosts. Remove dead services, update packages, check for open ports on the internet. Make sure hosts are referenced properly in Netbox. Check that monitoring works on the host. Remove personal keys from hosts. Check for NTP/DNS configuration.
- Make sure logrotate is working properly. Look for crontabs and document them in Confluence.
- Check your TODO-list. Raise important issues that haven’t been adressed. Remove dead subjects.
- Check UNIX tickets for open tasks. Remove unused tasks, raise important tasks
- Check ERP tickets. Close tickets with all actions done. Contact/bump customers to ask them if tickets can be closed. Add internal comments on what actions need to be done.


