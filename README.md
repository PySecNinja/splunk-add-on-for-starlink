# Splunk Add-On for Starlink Intrustions

## Overview

Install this add on on a universal forwarder in your starlink network. This will allow you to collect data from the starlink API and send it to Splunk for analysis.

### Prepare the environment 

1. ```python -m venv venv```
2. ```source venv/bin/activate```
3. ```pip install -r requirements.txt```

### Run the ```start_all_modes.sh``` script to start all modes of the Starlink API. This will run disk_grpc and create the loging structure bin/logs/* we will use inputs.conf to monitor these files and send them to splunk via hec or syslog.

# Splunk Preq
create 'index=starlink'

Starlink Scripts from this repo:
https://github.com/sparky8512/starlink-grpc-tools
