# Internet of Things Foundation Series

# Module 1: IoT Foundation: Telemetry

## The Telemetry Scenario
* Small company manufactures ice cream products and trucks them to stores in Seattle
* Challenges: in distribution is maintaining the cold chain
* What data you should collect?
* Tracking data point:
  * Using microcontroller to record measurements from: digital I/O, temperature, voltage at the freezer, time and day stamp
* We can implement IoT best practices:
  * First, take a reading every five seconds to know when different events occur
  * Each time we take a reading, take measurements from all sensors and assemble them into a single string to send to AWS IoT.
  * Track this in UTC/universal time
* What other data could you collect?
* Possible future data to collect:
  * Receive: temperature and humidity outside of the trailer, tire pressure, axle vibration, fuel level, gas cap opened or closed, miles on the engine, vehicle speed, gps location
  * Send: message to the driver to check the status of the freezer door, turn on the truck's backup battery, schedule maintenance for the refrigeration unit.

## Agenda
Establish communication with the sensor, collect and transform the data, and summarize it into a portal.
* Register a sensor within AWS
* Secure the sensor
* Establish communication with the sensor
* Collect data from the sensor
* Transform and visualize the data
* Review the best practices for Telemetry

## AWS IoT Core
* 6 main components: identity service, device gateway, message broker, rules engine, device shadow, registry.
* Identity Service: provides a secure communication channel for the devices to communicate with each other and other services. it provides authentication such as:
  * Mutual authentication (MQTT over TLS v1.2)
  * SigV4 over HTTP or MQTT over Websockets
  * Custom authentication
* Device Gateway: enables devices to securely and efficiently communicate with AWS IoT Core. It can exchange messages through AWS IoT Message Broker.
* Message Broker: processes and routes data from your devices into IoT Core.
  * Uses a Publish and Subscribe model to decouple devices and applications
  * Allows two-way message streaming between devices and applications
  * Provides data transformation, re-routing, and enhancement with external data resources
* Rules Engine: listens for incoming messages that match a rule
  * To route our device's data into AWS IoT Analytics.
* Device Shadow: used to store and retrieve current-state information for a thing (device, application)
* Registry: can be thought of as a database of devices.
  * Helps you manage your device ecosystem and acts as a repository for device certificates.

## Things and Devices
* Term "device" to refer to the physical entity, the term "thing" to refer to it's electronic or cloud-based form
* Thing: representation of a physical device or logical entity, like a lightbulb or sensor.
  * It also can have attributes
  * Can be associated to a thing type but can be associated to only one thing type at a time.
* Thing type: a method to organize things into logical categories; such as lightbulbs, thermostats, and motion sensors
  * After thing types are created, you cannot change their name
  * If a thing type is deprecated, you can decide whether to keep it for historical purposes or delete it.
* Thing group: allow you to manage several things at once.

## Security
* Securing devices
  * Authentication: certificates
  * Authorization: IoT policies, IAM roles
  * All communications is encrypted with Transport Layer Security v1.2
* Device Authentication
  * Benefits: asymmetric keys can be used with devices, strong client authentication
  * X.509 certificates
  * Connected devices must support the following in their TLS: TLS 1.2, SHA-256 RSA certificate signature validation, one of the AWS IoT-supported TLS cipher suites
  * IoT policies: control access to the IoT data plane
  * IAM roles: grant AWS IoT Core access to other AWS services

## MQTT and AWS IoT Device Registry
* Message Queuing Telemetry Transport (MQTT): to make connections with remote locations where a 'small code footprint' is required or the network bandwidth is limited.
* Is a lightweight, open standard messaging protocol
* Provides bidirectional communication
* Uses: a publish/subscribe method, MQTT over TLS 1.2
* AWS IoT Device Registry is a catalog of static metadata and attributes about the devices, such as serial number, manufacture, firmware version, internal identifier, and device capabilities.
  * Catalog of static device metadata
  * Storage of records of your devices, their attributes
  * Repository of the device certificates
  * Fully managed
  * Highly scalable

## AWS IoT Rules Engine
* Is one of the primary methods of filtering and directing communication from AWS IoT Core to other AWS services.
* Helps IoT Core to interact with AWS services
* Monitor the MQTT topic stream
* Rules: use an SQL-like format to filter MQTT messages
* Remember: grant the rules engine the appropriate IAM role and permission

## Presenting the Data
* Analyzing the Data
  * AWS IoT Analytics
    * IoT data is noisy and contains gaps and false readings
    * Filter, process, transform, and enrich your data
    * Store raw data and processed data
    * Perform ad hoc queries or sophisticated IoT analytics and visualization
  * IoT Analytics process:
    * Create Channel and select the data
    * Configure Pipelines that support transformations
    * Store it in Data Stores for analysis
    * Query the dataset
    * Create visualization
* Visualizing the data
  * Amazon QuickSight to visualize data and perform ad hoc analysis.
* Best Practices
  * Things:
    * For things, you should utilize granular device IDs and associate them with the collected and aggregated device data.
    * For things, have the IoT device create the timestamp instead of when the data is uploaded.
  * Security:
    * Provide each device an unique certificate and key pair
    * Follow the strategy of least privilege
    * Ensure ClientID and thingName device connections match
  * Communication:
    * Consider the frequency that the device sends its data
  * Visualization:
    * Strategy should reflect the business outcome's KPIs
