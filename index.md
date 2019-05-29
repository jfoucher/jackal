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

<article class="post" id="latest">

  <header class="post-header">
    <h1 class="post-title">{{ post.title }}</h1>
    <time class="post-date" datetime="{{ post.date }}">
    {% assign m = post.date | date: "%b" %}
        {% case m %}
          {% when 'April' %}Printemps
          {% when 'May'  %}Printemps
          {% when 'June' %}Printemps
          {% when 'July' %}Été
          {% when 'August' %}Été
          {% when 'September' %}Été
          {% when 'October' %}Automne
          {% when 'November' %}Automne
          {% when 'December' %}Automne
          {% when 'January'  %}Hiver
          {% when 'February' %}Hiver
          {% when 'March' %}Hiver
          {% else %}{{ post.date | date: "%b" }}.
          {% endcase %}
        {{ post.date | date: "%Y" }}
    </time>
  </header>

  <div class="post-content pretty-links">
    {{ post.content }}
  </div>

</article>

{% endfor %}