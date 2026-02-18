# Merge the definition of a thing

{% capture command %}{% include_relative generated/commands/merge/mergethingdefinition.md %}{% endcapture %} {{ command
| markdownify }}

{% capture response %}{% include_relative generated/commands/merge/mergethingdefinitionresponse.md %}{% endcapture %} {{
response | markdownify }}

{% capture event %}{% include_relative generated/events/mergedthingdefinition.md %}{% endcapture %} {{ event |
markdownify }}

{% capture command %}{% include_relative generated/commands/merge/mergedeletethingdefinition.md %}{% endcapture %} {{
command | markdownify }}

