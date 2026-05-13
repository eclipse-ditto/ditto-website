# Modify the policy ID of a Thing

{% capture command %}{% include_relative generated/commands/modify/modifypolicyid.md %}{% endcapture %}
{{ command | markdownify }}

{% capture response %}{% include_relative generated/commands/modify/modifypolicyidresponsemodified.md %}{% endcapture %}
{{ response | markdownify }}

{% capture response %}{% include_relative generated/commands/modify/modifypolicyidresponsecreated.md %}{% endcapture %}
{{ response | markdownify }}

{% capture event %}{% include_relative generated/events/policyidcreated.md %}{% endcapture %}
{{ event | markdownify }}

{% capture event %}{% include_relative generated/events/policyidmodified.md %}{% endcapture %}
{{ event | markdownify }}
