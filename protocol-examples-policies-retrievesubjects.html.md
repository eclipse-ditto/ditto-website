# Retrieve subjects

{% capture command %}{% include_relative generated/commands/query/retrievesubjects.md %}{% endcapture %}
{{ command | markdownify }}

{% capture response %}{% include_relative generated/commands/query/retrievesubjectsresponse.md %}{% endcapture %}
{{ response | markdownify }}
