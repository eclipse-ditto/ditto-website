# Modify a single desired property

{% capture command %}{% include_relative generated/commands/modify/modifyfeaturedesiredproperty.md %}{% endcapture %}
{{ command | markdownify }}

{% capture response %}{% include_relative generated/commands/modify/modifyfeaturedesiredpropertyresponse.md %}{% endcapture %}
{{ response | markdownify }}

{% capture event %}{% include_relative generated/events/featuredesiredpropertymodified.md %}{% endcapture %}
{{ event | markdownify }}