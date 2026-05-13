# Retrieve property

{% capture command %}{% include_relative generated/commands/query/retrievefeatureproperty.md %}{% endcapture %}
{{ command | markdownify }}

{% capture response %}{% include_relative generated/commands/query/retrievefeaturepropertyresponse.md %}{% endcapture %}
{{ response | markdownify }}
