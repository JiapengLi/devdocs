# Mappers API

## Introduction

The Mappers API is a set of HTTP requests used for submitting data to the Mappers project. Data submitted is viewable on [mappers.helium.com](https://mappers.helium.com) and updated every eight hours starting at 01:30 UTC.

## Authentication

There is currently no authentication required.

{% api-method method="post" host="https://mappers.helium.wtf" path="/api/v1/ingest" %}
{% api-method-summary %}
Ingest Uplink
{% endapi-method-summary %}

{% api-method-description %}
Submit geo tagged device uplink.    
  
Content-Type: application/json  
Requests are intended to be sent from an HTTP integration within Console. Metadata from the standard JSON message is used in addition to the required fields detailed below.   
  
All required fields can be located at any level within the `decoded`JSON field.   
All of the following fields are required `latitude`, `longitude`, `altitude`, `accuracy`.   
The following fields are optional`hdop`, `sats`.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="latitude" type="number" required=true %}
Device Latitude Value
{% endapi-method-parameter %}

{% api-method-parameter name="longitude" type="number" required=true %}
Device Longitude Value
{% endapi-method-parameter %}

{% api-method-parameter name="altitude" type="number" required=true %}
Device Altitude Value
{% endapi-method-parameter %}

{% api-method-parameter name="accuracy" type="number" required=true %}
Device GPS Accuracy Value \(in meters\)
{% endapi-method-parameter %}

{% api-method-parameter name="sats" type="number" required=false %}
Device Visible Satellites Value \(1-16\)
{% endapi-method-parameter %}

{% api-method-parameter name="hdop" type="number" required=false %}
Device HDOP Value \(1-10\)
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Request submission successful
{% endapi-method-response-example-description %}

```
Success
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Required request parameters not found.
{% endapi-method-response-example-description %}

```
Invalid Fields
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



