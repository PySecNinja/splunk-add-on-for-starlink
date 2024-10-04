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

### Indexer Configuration

1. Install the app on your Splunk indexers.
   - The app will automatically detect and use the `indexes.conf` file.
   - Ensure that `inputs.conf` is disabled on indexers.

### Verification

After installation, verify that:
1. The `starlink` index is created and visible.
2. No unwanted inputs are enabled on the indexers.

### More Usage 

Run to see script in the background 

```ps aux | grep dish_grpc_text.py```

#### Stop And Start Scripts
```start_scripts_in_background.sh```
```stop _scripts_in_background.sh```

## Additional Resources

Starlink scripts utilized in this add-on can be found in the following repository:
[Starlink gRPC Tools](https://github.com/sparky8512/starlink-grpc-tools)

## TODO

- [ ] Move logs into the sample logs directory.
- [ ] Implement a method to send Starlink logs to Splunk.
- [ ] Create Dashboards from the Data pulled.
- [ ] Create Alerts
