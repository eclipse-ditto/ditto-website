# Create a subject

{% capture command %}{% include_relative generated/commands/modify/modifysubject.md %}{% endcapture %}
{{ command | markdownify }}

{% capture response %}{% include_relative generated/commands/modify/modifysubjectresponse.md %}{% endcapture %}
{{ response | markdownify }}

