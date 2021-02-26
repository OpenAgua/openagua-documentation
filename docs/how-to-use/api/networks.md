# networks

{% api-method method="get" host="https://www.openagua.org/api" path="/v1/networks/:network\_id" %}
{% api-method-summary %}
networks
{% endapi-method-summary %}

{% api-method-description %}
Get a network, with various options for downloading in different formats and including related data.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="network\_id" type="number" required=true %}
ID of the network to get.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-query-parameters %}
{% api-method-parameter name="purpose" type="string" required=false %}
This is a way of specifying the purpose of the request. If omitted, the normal, JSON-formatted version of the network will be returned.  
For now, the only option is "download".
{% endapi-method-parameter %}

{% api-method-parameter name="format" type="string" required=false %}
If the purpose is "download", the "format" parameter is used to specify the file format of the download.  
Options include "json", "csv", "xlsx", "adjacency", "geojson" and "shapefile".
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

