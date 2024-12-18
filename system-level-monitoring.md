# Linux system monitoring

## General strategy

All the thresholds  mentionned in this document are generic values and should be adapted to each customer specificities.  
As a thumbrule, warning value can be set to twice/half the critical value.  
If available, predictive alarms based on value derivation should be set to prevent reaching critical value of system ressources. Any prediction on a time period of more than a few hours tend to produce a lot of false positive alerts, thus those alarms should only be set during open hours.  

In any case, accuratly setting the services dependencies helps a lot to analyse an outage by reducing the amount of alerts created as a consequence of a root problem.  
Trivial exemple:
- Insuffisant disk space causing a database crash and a website not responding correctly. Setting the dependencies properly allows identifying directly the root cause.  

As a drawback, teams that are used to receive a lot of alerts in case something is "really going wrong" need to reajust their process when putting this in place.

## Metric monitoring

### Mandatory

- CPU usage
	- A special attention should be paid to this value (usage percentage of the total amount of cpu vs of one core).
	- Indicative critical value: 95% of CPU usage

- RAM usage
	- The most valuable indicator on a linux system is the available memory for application allocation (MemAvailable in /proc/meminfo).
	- Indicative critical values: 100 MB / 5%

- FS space/inode and usage
	- All mounted FS should be monitored.
	- Indicative critical value: 90% (used) / 2GB (free)

- Disk I/O
	- Block device iops, troughput and operation latency are critical for system performances
	- Indicative critical value
		- NVME ssd : Tenths of thousand IOPS, 0.1ms latency
		- HDD :  around 200 IOPS, 150 to 200 MBbps througput and above 5ms latency
		- SAN lun : hardware and san-type dependant

- Swap I/O
	- Modern system with swap available should use it to unload any rarely used memory segment. The important metric to consider is the swap in/out operations that should remain at a marginal level
	- Indicative critical value: 10 operations per second

- Network usage
	- Bandwidth usage
	- Indicative critical value: 80% of the link speed
	- In addition to the bandwidth internet facing network can benefit of a pps monitoring.

### Additionnal indicators that should be considered:

- Context switching
	- Increase of this value can indicate that the system will be soon overloaded.

- Interrupts
	- For systems with a lot of IOPS like software routers.

- System Load
	- System load should be considered only in relation to its "normal" value in operation.
	- Indicative critical value : number of CPU cores

## Alert triggering events

These are the lifecycle events that should/must trigger an alert

### Mandatory

- OOM kill

### Optional

- Unplanned reboot
- Timesync
- Dns resolution
