# Delete Feature Desired Properties

{% capture command %}{% include_relative generated/commands/modify/deletefeaturedesiredproperties.md %}{% endcapture %}
{{ command | markdownify }}

{% capture response %}{% include_relative generated/commands/modify/deletefeaturedesiredpropertiesresponse.md %}{% endcapture %}
{{ response | markdownify }}

{% capture event %}{% include_relative generated/events/featuredesiredpropertiesdeleted.md %}{% endcapture %}
{{ event | markdownify }}