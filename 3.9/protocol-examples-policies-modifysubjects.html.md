# Modify subjects

{% capture command %}{% include_relative generated/commands/modify/modifysubjects.md %}{% endcapture %}
{{ command | markdownify }}

{% capture response %}{% include_relative generated/commands/modify/modifysubjectsresponse.md %}{% endcapture %}
{{ response | markdownify }}

