---
layout: default
---

<div class="lead pretty-links"  markdown="1">
  Bonjour à toi cher lecteur. Je ne sais pas comment tu es arrivé ici, mais tu vas voir c'est vraiment "stream of consciousness"&hellip;

  J'écris sans filtres donc attention à toi l'ami !

  Par exemple, tu pourrais commencer par lire [l'article le plus récent](#latest) ?
</div>

---

{% for post in site.posts limit:1 %}
{::nomarkdown}
<article class="post" id="latest">

  <header class="post-header">
    <h1 class="post-title">{{ post.title }}</h1>
    <time class="post-date" datetime="{{ post.date }}">
    {% assign d = post.date | date: "%-d" %}
    {% assign m = post.date | date: "%B" %}
    {% case m %}
      {% when 'April' or 'May' or 'June' %}Printemps
      {% when 'July' or 'August' or 'September' %}Été
      {% when 'October' or 'Npvember' or 'December' %}Automne
      {% when 'January' or 'February' or 'March' %}Hiver
      {% else %}{{ post.date | date: "%b" }}.
      {% endcase %}
    {{ post.date | date: "%Y" }}
    </time>
  </header>

  <div class="post-content pretty-links">
    {{ post.content }}
  </div>

</article>


{:/}
{% endfor %}