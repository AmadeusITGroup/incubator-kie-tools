<!--
   Licensed to the Apache Software Foundation (ASF) under one
   or more contributor license agreements.  See the NOTICE file
   distributed with this work for additional information
   regarding copyright ownership.  The ASF licenses this file
   to you under the Apache License, Version 2.0 (the
   "License"); you may not use this file except in compliance
   with the License.  You may obtain a copy of the License at
     http://www.apache.org/licenses/LICENSE-2.0
   Unless required by applicable law or agreed to in writing,
   software distributed under the License is distributed on an
   "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
   KIND, either express or implied.  See the License for the
   specific language governing permissions and limitations
   under the License.
-->

# extended_services

![Version: 10.0.999](https://img.shields.io/badge/Version-10.0.999-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 10.0.999](https://img.shields.io/badge/AppVersion-10.0.999-informational?style=flat-square)

A Helm chart to deploy Extended Services on Kubernetes

## Values

| Key              | Type   | Default                                                                                                                                                                                                                                                | Description                                                                                                                                     |
| ---------------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| autoscaling      | object | `{"enabled":false,"maxReplicas":100,"minReplicas":1,"targetCPUUtilizationPercentage":80}`                                                                                                                                                              | Extended Services HorizontalPodAutoscaler configuration (https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale/)            |
| fullnameOverride | string | `""`                                                                                                                                                                                                                                                   | Overrides charts full name                                                                                                                      |
| image            | object | `{"account":"apache","name":"incubator-kie-sandbox-extended-services","pullPolicy":"IfNotPresent","registry":"docker.io","tag":"10.0.x"}`                                                                                                              | Image source configuration for the Extended Services image                                                                                      |
| imagePullSecrets | list   | `[]`                                                                                                                                                                                                                                                   | Pull secrets used when pulling Extended Services image                                                                                          |
| ingress          | object | `{"annotations":{},"className":"{{ .Values.global.kubernetesIngressClass }}","enabled":false,"hosts":[{"host":"extended-services.{{ .Values.global.kubernetesClusterDomain }}","paths":[{"path":"/","pathType":"ImplementationSpecific"}]}],"tls":[]}` | Extended Services Ingress configuration (https://kubernetes.io/docs/concepts/services-networking/ingress/)                                      |
| name             | string | `"extended-services"`                                                                                                                                                                                                                                  | The Extended Services application name                                                                                                          |
| nameOverride     | string | `""`                                                                                                                                                                                                                                                   | Overrides charts name                                                                                                                           |
| nodeSelector     | object | `{}`                                                                                                                                                                                                                                                   |                                                                                                                                                 |
| openshiftRoute   | object | `{"annotations":{},"enabled":false,"host":"extended-services.{{ .Values.global.openshiftRouteDomain }}","tls":{"insecureEdgeTerminationPolicy":"None","termination":"edge"}}`                                                                          | Extended Services OpenShift Route configuration (https://docs.openshift.com/container-platform/4.14/networking/routes/route-configuration.html) |
| service          | object | `{"nodePort":"","port":21345,"type":"ClusterIP"}`                                                                                                                                                                                                      | Extended Services Service configuration (https://kubernetes.io/docs/concepts/services-networking/service/)                                      |
| serviceAccount   | object | `{"annotations":{},"create":true,"name":""}`                                                                                                                                                                                                           | Extended Services ServiceAccount configuration (https://kubernetes.io/docs/concepts/security/service-accounts/)                                 |

---

Autogenerated from chart metadata using [helm-docs v1.13.1](https://github.com/norwoodj/helm-docs/releases/v1.13.1)
