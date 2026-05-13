# Merge all attributes of a thing

{% capture command %}{% include_relative generated/commands/merge/mergeattributes.md %}{% endcapture %} {{ command |
markdownify }}

{% capture response %}{% include_relative generated/commands/merge/mergeattributesresponse.md %}{% endcapture %} {{
response | markdownify }}

{% capture event %}{% include_relative generated/events/mergedattributes.md %}{% endcapture %} {{ event | markdownify }}

{% capture command %}{% include_relative generated/commands/merge/mergedeleteattributes.md %}{% endcapture %} {{ command
| markdownify }}

