# Delete a single feature

{% capture command %}{% include_relative generated/commands/modify/deletefeature.md %}{% endcapture %}
{{ command | markdownify }}

{% capture response %}{% include_relative generated/commands/modify/deletefeatureresponse.md %}{% endcapture %}
{{ response | markdownify }}

{% capture event %}{% include_relative generated/events/featuredeleted.md %}{% endcapture %}
{{ event | markdownify }}
