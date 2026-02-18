# Modify a single attribute

{% capture command %}{% include_relative generated/commands/modify/modifyattribute.md %}{% endcapture %}
{{ command | markdownify }}

{% capture response %}{% include_relative generated/commands/modify/modifyattributeresponse.md %}{% endcapture %}
{{ response | markdownify }}

{% capture event %}{% include_relative generated/events/attributemodified.md %}{% endcapture %}
{{ event | markdownify }}

