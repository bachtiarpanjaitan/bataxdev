---
layout: archive
author_profile: true
permalink: /
classes: wide
---

{{ content }}

{% capture banner %}
  [![Foo](/assets/images/banner.jpg)](/services)
{% endcapture %}

<figure>
  {{ banner | markdownify | remove: "<p>" | remove: "</p>" }}
</figure>


