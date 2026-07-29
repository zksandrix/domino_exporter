<h1>domino_exporter</h1>
A cross-platform utility for exporting Domino statistics to Prometheus. Works on Windows and Linux.<br/>
Tested:<br/>
1 - Windows Server 2019-2025<br/>
2 - Linux RHEL (requires glibc 2.34)<br/>
3 - Linux DEB (requires glibc 2.34)

## Installation
To install, place the executable file in the domino directory (where the nnotes.dll or nnotes.so library is located) and run it.

## Notes.ini
By default, domino_exporter runs on port 9100 and updates information every 30 seconds. There are two parameters to change these values:<br/>
1 - DOMINO_EXPORTER_PORT - to change the port.<br/>
2 - DOMINO_EXPORTER_STATISTICS_UPDATE_INTERVAL - to change the statistics update interval. In seconds.