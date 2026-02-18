# Merge a single attribute of a thing

{% capture command %}{% include_relative generated/commands/merge/mergeattribute.md %}{% endcapture %} {{ command |
markdownify }}

{% capture response %}{% include_relative generated/commands/merge/mergeattributeresponse.md %}{% endcapture %} {{
response | markdownify }}

{% capture event %}{% include_relative generated/events/mergedattribute.md %}{% endcapture %} {{ event | markdownify }}

{% capture command %}{% include_relative generated/commands/merge/mergedeleteattribute.md %}{% endcapture %} {{ command
| markdownify }}

