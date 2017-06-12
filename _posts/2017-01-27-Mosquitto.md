---
layout: post
title: "Mosquitto and MQTT"
date: 2017-1-27
---

Learning a bit about MQTT using Mosquitto for Hillcrest Hackday.

Installing tools for Ubuntu:

```bash
# sudo apt-get install mosquitto libmosquitto-dev mosquitto-clients
# sudo service mosquitto status
```

Subscribing to a topic with command line:

```bash
# mosquitto_sub -h localhost -t "mqtt" -v
```

Sending a message to a topic with command line:

```bash
# mosquitto_pub -h localhost -t "mqtt" -m "Hello MQTT World."
```

Installing Python module:
```bash
# sudo pip install paho-mqtt
```

Testing that in python:
```python
import paho.mqtt.client as paho
client = paho.Client()
```

A simple client that connects to a server, subscribes to a topic,
responds to messages by publishing a different message on a different
topic:

```python
#!/bin/python

import paho.mqtt.client as paho
import string

def onConnect(client, userdata, flags, rc):
    print "Connected."

    client.subscribe("lidarCtl")

def onMessage(client, userdata, msg):
    print(msg.topic+" "+str(msg.payload))
    client.publish("mqtt", "Client got request.")

client = paho.Client()
client.on_connect = onConnect
client.on_message = onMessage

client.connect("localhost")

client.loop_forever()
```








