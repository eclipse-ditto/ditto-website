# Merge all desired properties of a feature

{% capture command %}{% include_relative generated/commands/merge/mergefeaturedesiredproperties.md %}{% endcapture %} {{
command | markdownify }}

{% capture response %}{% include_relative generated/commands/merge/mergefeaturedesiredpropertiesresponse.md %}{%
endcapture %} {{ response | markdownify }}

{% capture event %}{% include_relative generated/events/mergedfeaturedesiredproperties.md %}{% endcapture %} {{ event |
markdownify }}

{% capture command %}{% include_relative generated/commands/merge/mergedeletefeaturedesiredproperties.md %}{% endcapture
%} {{ command | markdownify }}

