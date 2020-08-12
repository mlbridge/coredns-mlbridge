# CoreDNS-MLBridge

[![GitHub license](https://img.shields.io/github/license/mlbridge/coredns-mlbridge)](https://github.com/mlbridge/coredns-mlbridge/blob/master/LICENSE)

![GSoC Icon](https://developers.google.com/open-source/gsoc/resources/downloads/GSoC-logo-horizontal-200.png)


This repository contains the plugin for connecting the CoreDNS server to a 
Machine Learning Environment for DNS request and response analysis, monitoring 
and alerting.

This can be modified to work for any other platform as well as language which 
does not have machine learning capabilities. 

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

To add the plugin to a particular port say 1053, please make the changes to the
Corefile as shown below:

```
.:1053 {
    mlplugin
}
```

## MLBridge Plugin

The mlbridge plugin is a CoreDNS plugin that forwards requests to the 
mlbridge-middleware app via HTTP POST requests. Once the mlbridge-middleware app
processes the request,it sends the prediction, whether the domain name is 
malicious or benign, back to the plugin. Depending on the nature of the domain 
name, the plugin can be configured to allow the request to fall through to the 
other plugins or send the request to a honeypot or a blackhole.
