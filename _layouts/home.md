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

Batax Developer is a business engaged in the creation and development of software, hardware, system design and maintenance services


