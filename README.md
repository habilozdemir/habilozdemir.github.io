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

{% assign aylar = "Ocak,Şubat,Mart,Nisan,Mayıs,Haziran,Temmuz,Ağustos,Eylül,Ekim,Kasım,Aralık" | split: "," %}
{% assign sorted_items = "" | split: "" %}
{% for page in site.pages %}
  {% if page.name contains '.md' and page.name != 'README.md' %}
    {% assign clean_name = page.name | remove: '.md' %}
    {% assign p = clean_name | split: '-' %}
    {% assign gun = p[0] %}
    {% assign ay = p[1] %}
    {% assign yil = p[2] %}
    {% assign saat = p[3] %}
    {% assign dakika = p[4] %}
    {% assign ay_index = ay | minus: 1 %}
    {% assign ay_adi = aylar[ay_index] %}
    {% capture okunakli_tarih %}{{ gun }} {{ ay_adi }} {{ yil }}, {{ saat }}:{{ dakika }}{% endcapture %}
    {% capture sort_key %}{{ yil }}-{{ ay }}-{{ gun }}-{{ saat }}-{{ dakika }}|{{ page.url | relative_url }}|{{ okunakli_tarih }}{% endcapture %}
    {% assign sorted_items = sorted_items | push: sort_key %}
  {% endif %}
{% endfor %}
{% assign sorted_items = sorted_items | sort | reverse %}

<ul>
  {% for item in sorted_items %}
    {% assign parts = item | split: '|' %}
    {% assign link_url = parts[1] %}
    {% assign link_tarih = parts[2] %}
    <li><a href="{{ link_url }}">{{ link_tarih }}</a></li>
  {% endfor %}
</ul>

## Hakkımda

İslam mantığı ve sermaye piyasalarıyla ilgileniyorum. Sakarya'da ilk ve ortaöğrenimimi tamamladıktan sonra Apple Digital Masters ve Tidal MQA programlarına katılarak çeşitli projelerde görev aldım. 2021'den sonra odağımı finansal piyasalara çevirdim.
