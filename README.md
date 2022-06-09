# carvel

## RabbitMQ

RabbitMQ is an open source general-purpose message broker that is designed for consistent, highly-available messaging scenarios (both synchronous and asynchronous).

Overview of RabbitMQ

Trademarks: This software listing is packaged by Bitnami. The respective trademarks mentioned in the offering are owned by the respective companies, and use of them does not imply any affiliation or endorsement.

### Parameters

Configuration Reference

You can configure the following:

### Common parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|auth.rabbitmqPassword|Rabbitmq user's password|string|mypassword|
|auth.rabbitmqErlangCookie|Rabbitmq rabbitmq erlang cookie|string|""|

### Statefulset parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|StatefulSet.replicaCount|Number of RabbitMQ replicas to deploy|integer|1|
|StatefulSet.prometheus.io/port|RabbitMQ prometheus.io/port|integer|'9419'|
|StatefulSet.securityContext.fsGroup|Set RabbitMQ pod's Security Context fsGroup|integer|1001|
|StatefulSet.securityContext.terminationGracePeriodSeconds|Set RabbitMQ pod's termination grace period seconds|integer|120|
|StatefulSet.securityContext.runAsUser|Set RabbitMQ Security Context runAsUser|integer|0|
|StatefulSet.containers.runAsUser|Set RabbitMQ containers Security Context runAsUser|integer|1001|
|StatefulSet.containers.rabbitmqUlimitN0files|Set RabbitMQ containers RABBITMQ ULIMIT NOFILES|integer|65536|
|StatefulSet.ports.epmd|Enable epmd port|integer|4369|
|StatefulSet.ports.amqp|Amqp service port|integer|5672|
|StatefulSet.ports.amqpTls|Amqp TLS service port|integer|5671|
|StatefulSet.ports.dist|Erlang distribution service port|integer|25672|
|StatefulSet.ports.stats|RabbitMQ Manager service port|integer|15672|
|StatefulSet.ports.metrics|RabbitMQ Prometheues metrics service port|integer|9419|
|StatefulSet.livenessProbe.enabled|Enable livenessProbe|string|true|
|StatefulSet.livenessProbe.initialDelaySeconds|Initial delay seconds for livenessProbe|integer|120|
|StatefulSet.livenessProbe.periodSeconds|Period seconds for livenessProbe|integer|30|
|StatefulSet.livenessProbe.timeoutSeconds|Timeout seconds for livenessProbe|integer|20|
|StatefulSet.livenessProbe.failureThreshold|Failure threshold for livenessProbe|integer|6|
|StatefulSet.livenessProbe.successThreshold|Success threshold for livenessProbe|integer|1|
|StatefulSet.readinessProbe.enabled|Enable readinessProbe|string|true|
|StatefulSet.readinessProbe.initialDelaySeconds|Initial delay seconds for readinessProbe|integer|10|
|StatefulSet.readinessProbe.periodSeconds|Period seconds for readinessProbe|integer|30|
|StatefulSet.readinessProbe.timeoutSeconds|Timeout seconds for readinessProbe|integer|20|
|StatefulSet.readinessProbe.failureThreshold|Failure threshold for readinessProbe|integer|3|
|StatefulSet.readinessProbe.successThreshold|Success threshold for readinessProbe|integer|1|
|StatefulSet.startupProbe.enabled|Enable startupProbe|string|false|
|StatefulSet.startupProbe.initialDelaySeconds|Initial delay seconds for startupProbe|integer|10|
|StatefulSet.startupProbe.periodSeconds|Period seconds for startupProbe|integer|30|
|StatefulSet.startupProbe.timeoutSeconds|Timeout seconds for startupProbe|integer|20|
|StatefulSet.startupProbe.failureThreshold|Failure threshold for startupProbe|integer|3|
|StatefulSet.startupProbe.successThreshold|Success threshold for startupProbe|integer|1|

### Persistence parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|StatefulSet.persistence.size|PVC Storage Request for RabbitMQ data volume|integer|8Gi|

### Exposure parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|Service.type|Kubernetes Service type|string|ClusterIP|
|Service.ports.amqp|Amqp service port|integer|5672|
|Service.ports.dist|Erlang distribution service port|integer|25672|
|Service.ports.stats|RabbitMQ Manager service port|integer|15672|
|Service.ports.metrics|RabbitMQ Prometheues metrics service port|integer|9419|
|Service.ports.epmd|EPMD Discovery service port|integer|4369|
|networkpolicy.enabled|Enable networkPolicy|string|false|
|networkpolicy.ports.epmd|Enable epmd port|integer|4369|
|networkpolicy.ports.amqp|Amqp service port|integer|5672|
|networkpolicy.ports.amqpTls|Amqp TLS service port|integer|5671|
|networkpolicy.ports.dist|Erlang distribution service port|integer|25672|
|networkpolicy.ports.manager|RabbitMQ Manager service port|integer|15672|
|networkpolicy.ports.metrics|RabbitMQ Prometheues metrics service port|integer|9419|
|ingress.enabled|Enable ingress|string|false|
