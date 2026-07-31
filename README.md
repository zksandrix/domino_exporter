<h1>domino_exporter</h1>
A cross-platform utility for exporting HCL Domino statistics to Prometheus. Works on Windows and Linux.<br/>
Tested on OS:<br/>
&nbsp;&nbsp;&nbsp;1 - Windows Server 2019-2025<br/>
&nbsp;&nbsp;&nbsp;2 - Linux RHEL (requires glibc 2.34)<br/>
&nbsp;&nbsp;&nbsp;3 - Linux DEB (requires glibc 2.34)<br/>
Tested on HCL Domino:<br/>
&nbsp;&nbsp;&nbsp;1 - HCL Domino 12.0.2<br/>
&nbsp;&nbsp;&nbsp;2 - HCL Domino 14.0<br/>
&nbsp;&nbsp;&nbsp;3 - HCL Domino 14.5<br/>
&nbsp;&nbsp;&nbsp;4 - HCL Domino 14.5.1<br/>

## Installation
To install, place the executable file in the domino directory (where the nnotes.dll or nnotes.so library is located) and run it.

## What is reflected in the metrics
Statistics are formatted to contain only alphanumeric characters. Other characters are replaced with the _ symbol.<br/>
Example:<br/>
&nbsp;&nbsp;&nbsp;Server.MailBoxes = Server_MailBoxes<br/>
&nbsp;&nbsp;&nbsp;Monitor.Last.EVENT MONITOR.Warning(High) = Monitor_Last_EVENT MONITOR_Warning_High_<br/>
<br/>
Only statistics with a numerical value are included in the metrics; date or text are not included (this is a Prometheus feature).<br/>
Example:<br/>
&nbsp;&nbsp;&nbsp;NO - Server.Task = Cluster Replicator: Idle: [08/01/2026 02:08:41 ZE1]<br/>
&nbsp;&nbsp;&nbsp;NO - Server.ElapsedTime = 00:34:03<br/>
&nbsp;&nbsp;&nbsp;YES - Server.ElapsedTimeDays = 0.023645833333333<br/>
&nbsp;&nbsp;&nbsp;YES - Server.MailBoxes = 1<br/>

## Notes.ini
By default, domino_exporter runs on port 9100 and updates information every 30 seconds. There are two parameters to change these values:<br/>
1 - DOMINO_EXPORTER_PORT - to change the port.<br/>
2 - DOMINO_EXPORTER_STATISTICS_UPDATE_INTERVAL - to change the statistics update interval. In seconds.