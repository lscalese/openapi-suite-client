 [![Gitter](https://img.shields.io/badge/Available%20on-Intersystems%20Open%20Exchange-00b2a9.svg)](https://openexchange.intersystems.com/package/openapi-suite-client)
 [![Quality Gate Status](https://community.objectscriptquality.com/api/project_badges/measure?project=intersystems_iris_community%2Fopenapi-suite-client&metric=alert_status)](https://community.objectscriptquality.com/dashboard?id=intersystems_iris_community%2Fopenapi-suite-client)
 [![Reliability Rating](https://community.objectscriptquality.com/api/project_badges/measure?project=intersystems_iris_community%2Fopenapi-suite-client&metric=reliability_rating)](https://community.objectscriptquality.com/dashboard?id=intersystems_iris_community%2Fopenapi-suite-client)

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg?style=flat&logo=AdGuard)](LICENSE)
# openapi-suite-client

This tiny an http client for [openapi-suite](https://openexchange.intersystems.com/package/OpenAPI-Suite).  

It's useful if you want to generate code from a remote openapi-suite installation.  

## Installation zpm

```
zpm "install openapi-suite-client"
```

## Installation docker

Clone/git pull the repo into any local directory

```
git clone https://github.com/intersystems-community/openapi-suite-client.git
```

Open the terminal in this directory and call the command to build and run InterSystems IRIS in container:

```
docker-compose up -d
```

To open IRIS Terminal do:

```
docker-compose exec iris iris session iris -U IRISAPP
```

## Usage

```
; remote openapi-suite rest service url : 
Set server = "https://openapisuite.demo.community.intersystems.com/openapisuite"

; Specification could be an URL, filepath or a stream.
Set specification = "https://petstore3.swagger.io/api/v3/openapi.json"

; Package name for generated classes.
Set packageName = "petstoreclient"

; available type : 
; - "client" : to generate http client classes. 
; - "production" :  to generate production client classes.
; - "rest" : to generate REST server classes
Set type = "client"


Set sc = ##class(dc.openapi.suite.client.RemoteCodeGen).Generate(specification, packageName, type, server)
```

More information about open-suite are available on this [DC article](https://community.intersystems.com/post/openapi-suite).  
