# CoreDNS-MLBridge

This repository contains the plugin for connecting the CoreDNS server to a 
Machine Learning Environment for DNS request and response analysis, monitoring 
and alerting.

## Installation

Clone the repository:
```
git clone https://github.com/mlbridge/coredns-mlbridge.git
```

Install Elasticsearch by following the instructions from this 
[link](https://phoenixnap.com/kb/install-elasticsearch-ubuntu). Start the 
Elasticsearch server.

To install and start CoreDNS please take a look at the CoreDNS 
[repository](https://github.com/coredns/coredns). Add the `mlbridge` plugin to
CoreDNS. To add external plugins, please take a look at the 
[example plugin](https://github.com/coredns/example).





```
cd mlbridge-ui/mlbridge_ui/src
python3 ui.py
```
