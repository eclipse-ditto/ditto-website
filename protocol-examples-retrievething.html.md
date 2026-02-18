# Retrieve a Thing

{% capture command %}{% include_relative generated/commands/query/retrievething.md %}{% endcapture %}
{{ command | markdownify }}

{% capture command %}{% include_relative generated/commands/query/retrievething-withfieldselector.md %}{% endcapture %}
{{ command | markdownify }}

{% capture response %}{% include_relative generated/commands/query/retrievethingresponse.md %}{% endcapture %}
{{ response | markdownify }}
