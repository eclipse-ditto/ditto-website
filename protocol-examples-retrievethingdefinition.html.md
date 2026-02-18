# Retrieve a definition

{% capture command %}{% include_relative generated/commands/query/retrievethingdefinition.md %}{% endcapture %}
{{ command | markdownify }}

{% capture response %}{% include_relative generated/commands/query/retrievethingdefinitionresponse.md %}{% endcapture %}
{{ response | markdownify }}
