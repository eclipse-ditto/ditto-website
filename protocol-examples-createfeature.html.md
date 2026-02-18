# Create a single feature

{% capture command %}{% include_relative generated/commands/modify/modifyfeature.md %}{% endcapture %}
{{ command | markdownify }}

{% capture response %}{% include_relative generated/commands/modify/modifyfeatureresponse.md %}{% endcapture %}
{{ response | markdownify }}

{% capture event %}{% include_relative generated/events/featurecreated.md %}{% endcapture %}
{{ event | markdownify }}
