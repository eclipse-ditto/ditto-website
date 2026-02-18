# Merge a single feature of a thing

{% capture command %}{% include_relative generated/commands/merge/mergefeature.md %}{% endcapture %} {{ command |
markdownify }}

{% capture response %}{% include_relative generated/commands/merge/mergefeatureresponse.md %}{% endcapture %} {{
response | markdownify }}

{% capture event %}{% include_relative generated/events/mergedfeature.md %}{% endcapture %} {{ event | markdownify }}

{% capture command %}{% include_relative generated/commands/merge/mergedeletefeature.md %}{% endcapture %} {{ command |
markdownify }}

