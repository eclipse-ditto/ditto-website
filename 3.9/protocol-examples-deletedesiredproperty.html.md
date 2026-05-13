# Delete a single desired property

{% capture command %}{% include_relative generated/commands/modify/deletefeaturedesiredproperty.md %}{% endcapture %}
{{ command | markdownify }}

{% capture response %}{% include_relative generated/commands/modify/deletefeaturedesiredpropertyresponse.md %}{% endcapture %}
{{ response | markdownify }}

{% capture event %}{% include_relative generated/events/featuredesiredpropertydeleted.md %}{% endcapture %}
{{ event | markdownify }}