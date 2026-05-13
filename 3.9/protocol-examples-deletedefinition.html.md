# Delete Feature Definition

{% capture command %}{% include_relative generated/commands/modify/deletefeaturedefinition.md %}{% endcapture %}
{{ command | markdownify }}

{% capture response %}{% include_relative generated/commands/modify/deletefeaturedefinitionresponse.md %}{% endcapture %}
{{ response | markdownify }}

{% capture event %}{% include_relative generated/events/featuredefinitiondeleted.md %}{% endcapture %}
{{ event | markdownify }}
