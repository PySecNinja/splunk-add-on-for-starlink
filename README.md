# Splunk Add-On for Starlink

## Overview

This add-on is designed to be installed on a universal forwarder within your Starlink network. It enables the collection of data from the Starlink API, which can then be sent to Splunk for comprehensive analysis.

## Environment Preparation on UF host

To set up the environment, follow these steps:

1. Create a virtual environment:
   ```bash
   python -m venv venv
   ```
2. Activate the virtual environment:
   ```bash
   source venv/bin/activate
   ```
3. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Running the Starlink API

Execute the `start_all_modes.sh` script to initiate all modes of the Starlink API. This script will run `disk_grpc` and establish the logging structure at `bin/logs/*`. We will use `inputs.conf` to monitor these files and send them to Splunk via HEC or syslog.

## Splunk Prerequisites

Ensure that you have created the following index in Splunk:
```index=starlink```


## Additional Resources

Starlink scripts utilized in this add-on can be found in the following repository:
[Starlink gRPC Tools](https://github.com/sparky8512/starlink-grpc-tools)

## TODO

- [ ] Move logs into the sample logs directory.
- [ ] Implement a method to send Starlink logs to Splunk.
- [ ] Create Dashboards from the Data pulled.
- [ ] Create Alerts
