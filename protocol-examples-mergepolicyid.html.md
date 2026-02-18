# Merge a policy id of a thing

{% capture command %}{% include_relative generated/commands/merge/mergepolicyid.md %}{% endcapture %} {{ command |
markdownify }}

{% capture response %}{% include_relative generated/commands/merge/mergepolicyidresponse.md %}{% endcapture %} {{
response | markdownify }}

{% capture event %}{% include_relative generated/events/mergedpolicyid.md %}{% endcapture %} {{ event | markdownify }}
