# Create a definition

{% capture command %}{% include_relative generated/commands/modify/modifythingdefinition.md %}{% endcapture %}
{{ command | markdownify }}

{% capture response %}{% include_relative generated/commands/modify/modifythingdefinitionresponsecreated.md %}{% endcapture %}
{{ response | markdownify }}

{% capture event %}{% include_relative generated/events/thingdefinitioncreated.md %}{% endcapture %}
{{ event | markdownify }}
