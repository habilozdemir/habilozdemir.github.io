Nostr ile merkeziyetsiz olarak yedekleniyor. GitHub [deposunu](https://github.com/habilozdemir/habilozdemir.github.io) inceleyebilir ya da [GitHub](https://github.com/habilozdemir) veya [Primal profilimi](https://primal.net/p/nprofile1qqsv2e8ujvex93z5z2ul2j8u4chczrk93l5j5fqmlrt7z5p6gmwu5rqe7qknh) ziyaret edebilirsiniz, ilginize minnet duyuyorum.

## Arşivlerim

* [quran-digital-archive](https://github.com/habilozdemir/quran-digital-archive)
* [nostr-archive](https://github.com/habilozdemir/nostr-archive)
* [mastodon-archive](https://github.com/habilozdemir/mastodon-archive)
* [medium-archive](https://github.com/habilozdemir/medium-archive)
* [medium-archive-2](https://github.com/habilozdemir/medium-archive-2)
* [notes-archive](https://github.com/habilozdemir/notes-archive)
* [mantik.blog](https://github.com/habilozdemir/mantik.blog)
* [habil-ozdemirin-yazilari](https://github.com/habilozdemir/habil-ozdemirin-yazilari)

## Notlarım

{% assign sorted_items = "" | split: "" %}
{% for page in site.pages %}
  {% if page.name contains '.md' and page.name != 'README.md' %}
    {% assign clean_name = page.name | remove: '.md' %}
    {% assign p = clean_name | split: '-' %}
    {% capture sort_key %}{{ p[2] }}-{{ p[1] }}-{{ p[0] }}-{{ p[3] }}-{{ p[4] }}|{{ page.url | relative_url }}|{{ clean_name }}{% endcapture %}
    {% assign sorted_items = sorted_items | push: sort_key %}
  {% endif %}
{% endfor %}
{% assign sorted_items = sorted_items | sort | reverse %}

<ul>
  {% for item in sorted_items %}
    {% assign parts = item | split: '|' %}
    <li><a href="{{ parts[1] }}">{{ parts[2] }}</a></li>
  {% endfor %}
</ul>
