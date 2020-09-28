.. mu_mqtt documentation master file, created by
   sphinx-quickstart on Sun Aug 30 03:00:07 2020.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to mu_mqtt's documentation!
=================================

mu_mqtt created to view the MQTT broker messages

.. toctree::
   :maxdepth: 2
   :caption: Contents:



Usage
==================

Create ``docker-compose.yml``

.. code:: yaml

    ---
    # .docker-compose.yml
    version: '3.1'
    services:
    mqtt_server:
        image: eclipse-mosquitto
        container_name: mqtt_server
        restart: unless-stopped
        ports:
        - 1883:1883
    mqtt_viewer:
        image: belazy/mu_mqtt:latest
        container_name: mqtt_viewer
        restart: unless-stopped
        ports:
        - 5000:5000
        environment:
        MQTT_SERVER: 192.168.0.6

>>> docker-compose up -d