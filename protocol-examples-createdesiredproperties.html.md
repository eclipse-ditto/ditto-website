# Create Feature Desired Properties

{% capture command %}{% include_relative generated/commands/modify/modifyfeaturedesiredproperties.md %}{% endcapture %}
{{ command | markdownify }}

{% capture response %}{% include_relative generated/commands/modify/modifyfeaturedesiredpropertiesresponse.md %}{% endcapture %}
{{ response | markdownify }}

{% capture event %}{% include_relative generated/events/featuredesiredpropertiescreated.md %}{% endcapture %}
{{ event | markdownify }}