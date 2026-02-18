# Modify Feature Definition

{% capture command %}{% include_relative generated/commands/modify/modifyfeaturedefinition.md %}{% endcapture %}
{{ command | markdownify }}

{% capture response %}{% include_relative generated/commands/modify/modifyfeaturedefinitionresponse.md %}{% endcapture %}
{{ response | markdownify }}

{% capture event %}{% include_relative generated/events/featuredefinitionmodified.md %}{% endcapture %}
{{ event | markdownify }}
