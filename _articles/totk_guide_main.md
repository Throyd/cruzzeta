---
game-id: id: TLOZ-TOTK
title: Página principal de la guía
type: guide
navigation: main-page
---
Esto es la gúia

{% assign tips = site.articles | find_exp:"item", "item.game-id == page.game-id" | "item.type == guide" | "item.navigation == tip" %}
{% assign tips = site.articles | find_exp:"item", "item.game-id == page.game-id" | "item.type == guide" | "item.navigation == mission" %}
{% assign tips = site.articles | find_exp:"item", "item.game-id == page.game-id" | "item.type == guide" | "item.navigation == sanctuary" %}
{% assign tips = site.articles | find_exp:"item", "item.game-id == page.game-id" | "item.type == guide" | "item.navigation == temple" %}
{% assign tips = site.articles | find_exp:"item", "item.game-id == page.game-id" | "item.type == guide" | "item.navigation == gear" % | order}

<h4>Consejos</h4>
<h4>Misiones</h4>
<h4>Santuarios</h4>
<h4>Templos</h4>
<h4>Equipo</h4>
