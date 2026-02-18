# Merge all properties of a feature

{% capture command %}{% include_relative generated/commands/merge/mergefeatureproperties.md %}{% endcapture %} {{
command | markdownify }}

{% capture response %}{% include_relative generated/commands/merge/mergefeaturepropertiesresponse.md %}{% endcapture %}
{{ response | markdownify }}

{% capture event %}{% include_relative generated/events/mergedfeatureproperties.md %}{% endcapture %} {{ event |
markdownify }}

{% capture command %}{% include_relative generated/commands/merge/mergedeletefeatureproperties.md %}{% endcapture %} {{
command | markdownify }}

